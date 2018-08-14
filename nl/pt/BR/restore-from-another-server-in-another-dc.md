---

copyright:
  years: 1994, 2018
lastupdated: "2018-07-05"

---
{:pre: .pre}
{:new_window: target="_blank"}

# Criando um backup e restaurando dados de um VSI para outro em um data center diferente

Às vezes, você deseja restaurar dados para um servidor diferente. Este procedimento se aplica somente a restaurações de nível de arquivo de arquivos não S.O. Para restaurar uma imagem do sistema, siga as instruções de [Recuperação bare-metal do Windows](restoring-evault-bmr-system-volume-image.html).

O processo inclui registrar novamente o agente do EVault no segundo servidor para acessar o local do EVault do primeiro servidor e concluir uma **Restauração de outro computador**.

**Pré-requisitos**

- O Server1 e o Server2 devem ter o mesmo S.O. Restaurações de plataforma cruzada não são suportados.
- O Server1 e o Server2 devem ter agentes do EVAult que foram configurados anteriormente. Para aprender como configurar os agentes do EVault, clique [aqui](index.html#configuring-evault-agent-in-webcc).
- Uma tarefa de backup para o Server1 que produziu um backup para o local de EVault do Server1.

**Nota**: desative todas as tarefas de Planejamento em ambos os servidores para
evitar quaisquer conflitos. 

## Iniciando o WebCC de Server2

>**Nota**: lembre-se de iniciar sua conexão do {{site.data.keyword.BluVPN}} para obter acesso à rede privada do {{site.data.keyword.BluSoftlayer_full}} ou o link do WebCC não funcionará.

1. Efetue login no [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} e clique em **Armazenamento** > **Backup** no menu principal para exibir os servidores com o serviço de backup do EVault. 
2. Selecione Server2. Clique na seta de expansão que aponta para a direita para exibir o link do WebCC.
3. Clique em **Login do WebCC** para iniciar o cliente do WebCC em seu navegador.

## Registando o EVault

1. Clique em **Todos os agentes** e abra o agente específico que você deseja modificar.
2. Clique em **Editar** e selecione **Configurações de área segura**.
3. Clique em **Registrar** para conecta o Server1 ao Server2.
4. Na tela **Registrar novamente a área segura** para a entrada **Usar um perfil de área segura**, selecione **Inserir configurações de área segura**.
5. Insira o Nome da área segura, que é igual ao nome do EVault do Server1.
6. Insira as credenciais para o Server1 para efetuar login no EVault para o Server1.
7. Clique em **Carregar computadores**, essa ação exibe os servidores que estão conectados ao local da área segura.
8. Clique em **Salvar mudanças**.
9. Quando solicitado, clique em **Sim** para confirmar o novo registro do EVault.

## Executando a Tarefa de backup do Server1 como a Tarefa de restauração no Server2

1. Clique em **Todos os Agentes**.
   >**Nota**: você pode precisar atualizar a página para ver as tarefas que estão definidas no Server1 como acessíveis/sincronizadas na guia **Tarefas** do Server2
2. Passe o mouse sobre **Avançado** e selecione **Restaurar por meio de
outro computador**.
3. Na tela **Restaurar de outro computador**, clique em **Incluir**. Os campos são preenchidos automaticamente com valores padrão, portanto, mude-os.
4. Clique no campo Área segura e selecione **Inserir configurações de área segura** e digite o endereço IP da área segura do Server1. Clique em **Incluir**.
5. Atualize as credenciais para as credenciais do Server1.
6. Clique em **Salvar mudanças**. Essa ação conecta você à área segura do Server1.
7. Volte para a tela **Restaurar de outro computador**, atualize os campos Computador e Tarefa.
  - Computador: selecione Server1 como o computador de backup do qual restaurar. 
  - Tarefa: selecione a tarefa de backup de Server1.
8. Clique em **Avançar** para iniciar o processo de restauração para o server2 em outro Data center.
9. No prompt, insira a senha de backup e clique em **Avançar**.
10. Confirme se a tarefa de backup correta está selecionada e clique em **Avançar**. A tarefa de restauração agora está configurada no server2. 
11. Selecione a tarefa recém-configurada e clique em **Executar restauração**.
12. Selecione os arquivos que você deseja restaurar. 
13. Clique no sinal de mais para expandir a seleção de arquivo.
14. Clique na caixa de seleção dos arquivos ou pastas individuais a serem restauradas de server1 para server2. Em seguida, clique em **Incluir**.
15. Os arquivos preenchem a janela Conjunto de backup à direita. Clique em **Avançar**. 
16. Depois de concluir a seleção de dados, continue com a seleção de suas opções.
    - Selecione **Restaurar para o local original**.
    - Selecione **Sobrescrever arquivos existentes**.
17. Clique em **Executar restauração**. A janela Detalhes do processo fornece o status da tarefa de backup em execução. Após o backup ser concluído, clique em **Fechar**.


## Verificando a restauração

1. Conecte-se à raiz do Server2 por meio de SSH.
2. Liste os arquivos e todas as entradas de diretório em um formato longo.
  ```
  ls -la
  ```
  {: pre}
  
3. Compare a saída.
  
## Continuando o planejamento normal de Backup.

1. Quando a restauração for concluída, remova as informações de registro do server1, por meio do qual os
dados foram restaurados. 
2. Insira o registro atual do server2 e ative as tarefas de Planejamento.
