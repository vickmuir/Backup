---

copyright:
  years: 1994, 2018
lastupdated: "2018-05-31"

---
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Backup e restauração de um VSI para outro dentro do mesmo data center

Às vezes você deseja restaurar dados para um servidor diferente no mesmo data center. Estas instruções
ajudarão você a realizar essa tarefa. Este procedimento se aplica apenas a restaurações em nível de arquivo,
para arquivos que não sejam do S.O. Para restaurar uma imagem do sistema, siga as instruções de [Recuperação bare-metal do Windows](restoring-evault-bmr-system-volume-image.html).

Esse processo inclui registrar novamente o agente do EVault no segundo servidor para acessar o local do
EVault do primeiro servidor e executar **Restaurar por meio de outro computador**.


## Pré-requisitos

- O Server1 e o Server2 devem ter o mesmo S.O. Restaurações de plataforma cruzada não são suportados.
- O Server1 e o Server2 devem ter agentes do EVault configurados. Para saber como configurar os agentes
do EVault, clique [aqui](index.html#configuring-evault-agent-in-webcc)
- Uma tarefa de backup para o Server1 produziu um backup para o local do EVault do Server1.

**Nota**: desative todas as tarefas de Planejamento em ambos os servidores para
evitar quaisquer conflitos. 

## Iniciar WebCC de Server2

**Nota**: lembre-se de iniciar sua conexão do {{site.data.keyword.BluVPN}}
para obter acesso à rede privada do {{site.data.keyword.BluSoftlayer_full}} ou os links do WebCC não
funcionarão.

1. Efetue login no [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} e clique em **Armazenamento** > **Backup** no menu principal para exibir os servidores com o serviço de backup do EVault. 
2. Selecione Server2. Clique na seta de expansão que aponta para a direita para exibir o link do WebCC.
3. Clique em **Login do WebCC** para iniciar o cliente do WebCC em seu navegador.

## Registre o EVault:
1. Clique em **Todos os agentes** e abra o agente específico que você deseja
modificar.
2. Clique em **Editar** e selecione Configurações *Vault ".
3. Clique em **Registrar** para conecta o Server1 ao Server2.
4. Na tela **Registrar novamente a área segura** para a entrada **Usar um
perfil de área segura**, selecione **Inserir configurações de área segura**.
5. Insira o Nome da área segura, que é igual ao nome do EVault do Server1.
6. Insira as credenciais para o Server1 para efetuar login no EVault para o Server1.
7. Clique em **Carregar computadores**, isso exibe os servidores que estão
conectados ao local da área segura.
8. Clique em **Salvar Mudanças**.
9. Quando solicitado, clique em **Sim** para confirmar o novo registro do EVault.

## Execute a tarefa de backup do Server1 como a tarefa de restauração no Server2

1. Clique em **Todos os Agentes**. <br/> **Nota**: pode ser
necessário atualizar a página para ver as tarefas definidas no Server1 como acessíveis/sincronizadas
na guia **Tarefas** do Server2
2. Passe o mouse sobre **Avançado** e selecione **Restaurar por meio de
outro computador**.
3. Na tela **Restaurar por meio de outro computador**, faça as seleções a seguir:
  - Área segura: essa entrada deve ser padrão para o EVault do Server1
  - Computador: selecione Server1 como o computador de backup do qual restaurar. 
  - Tarefa: selecione a tarefa de backup no Server1.
4. Clique em **Avançar**
5. Confirme as informações de Origem
  - O **Local do conjunto de segurança** deve ser o local da Área segura do Server1.
  - Na seção **Selecionar uma versão de backup**, a versão de
backup especificada deve ser seu backup do Server1
  - A senha de criptografia deve ser a senha que você usou ao executar o backup no Server1.
6. Clique em **Avançar**
7. Seleção de dados: selecione quais arquivos precisam ser restaurados por meio do backup do Server1. Marque as caixas de seleção próximas aos arquivos e diretórios que deseja incluir e, em seguida, clique em **Incluir** para salvar as suas opções.
8. Clique em **Avançar** para mover para as opções de restauração.
9. Nas opções:
  - Destino: Selecione **Restaurar para o local original**
  - Sobrescrever Arquivo: Selecione **Sobrescrever arquivos existentes**
10. Clique em **Executar Restaurar**.
11. A tela Detalhe do processo exibe o status da tarefa de restauração.


## Verifique a restauração

1. Conecte-se à raiz do Server2 por meio de SSH.
2. Liste os arquivos, incluindo todas as entradas de diretório em um formato longo.
  ```
  ls -la
  ```
  {: pre}
  
3. Compare a saída.
  
## Continuar planejamento de backup normal.

1. Quando a restauração for concluída, remova as informações de registro do server1, por meio do qual os
dados foram restaurados. 
2. Insira o registro atual do server2 e ative as tarefas de Planejamento.
 

  

 
 
  
  
