---

copyright:
  years: 1994, 2019
lastupdated: "2019-08-01"

keywords: IBM Cloud backup,  EVault, Carbonite, backup, restore

subcollection: Backup

---
{:pre: .pre}
{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Restaurando dados de um VSI para outro dentro do mesmo data center
{: #restorefromotherVSI}

Às vezes você deseja restaurar dados para um servidor diferente no mesmo data center. Este procedimento se aplica somente a restaurações de nível de arquivo de arquivos não S.O. Para restaurar uma imagem do sistema, siga as instruções de [Recuperação bare-metal do Windows](/docs/infrastructure/Backup?topic=Backup-restoreBMR).

O processo inclui registrar novamente o agente de backup no segundo servidor para acessar a localização da área
segura do primeiro servidor e concluir uma **Restauração de outro computador**.

**Pré-requisitos**

- Server1 e Server2 devem ter o mesmo sistema operacional. Restaurações de plataforma cruzada não são suportados.
- O Server1 e o Server2 devem ter agentes de backup configurados anteriormente. Para obter mais informações sobre a configuração dos agentes de backup, consulte [Configurando o agente de backup no portal do {{site.data.keyword.backup_notm}}](/docs/infrastructure/Backup?topic=Backup-getting-started#getting-started).
- Uma tarefa de backup para o Server1 que produziu um backup para a localização da área segura do Server1.

Desative todas as tarefas planejadas em ambos os servidores para evitar quaisquer conflitos.
{:important}

## Iniciando o portal do {{site.data.keyword.backup_notm}} do Server2
{: #startWebCC}

Lembre-se de iniciar a sua conexão do {{site.data.keyword.BluVPN}} para obter acesso à rede privada do {{site.data.keyword.cloud}}, ou o link do portal do {{site.data.keyword.backup_notm}} não funcionará.
{:tip}

1. Efetue login no console do [{{site.data.keyword.cloud_notm}}](https://{DomainName}){: external}. No menu de navegação, selecione **Infraestrutura clássica**.
2. Clique em **Armazenamento** > **Backup em nuvem** para exibir os servidores com serviço de backup.
3. Selecione Server2. Clique
na seta de expansão para revelar o link do portal do {{site.data.keyword.backup_notm}}.
4. Clique em **Login do portal do {{site.data.keyword.backup_notm}}** para iniciar o cliente do portal em seu navegador.

## Registrando novamente a área segura
{: #reregistervault}

1. Clique em **Todos os agentes** e abra o agente específico que você deseja modificar.
2. Clique em **Editar** e selecione **Configurações de área segura**.
3. Clique em **Registrar** para conecta o Server1 ao Server2.
4. Na tela **Registrar novamente a área segura** para a entrada **Usar um perfil de área segura**, selecione **Inserir configurações de área segura**.
5. Insira o nome da área segura, que é o mesmo da área segura do Server1.
6. Insira as credenciais para o Server1 para efetuar login na área segura do Server1.
7. Clique em **Carregar computadores**, essa ação exibe os servidores que estão conectados ao local da área segura.
8. Clique em **Salvar mudanças**.
9. Quando solicitado, clique em **Sim** para confirmar o novo registro da área segura.

## Executando a tarefa de backup por meio do Server1 como a tarefa de restauração no Server2
{: #runbackuprestore}

1. Clique em **Todos os Agentes**.

   Talvez seja necessário atualizar a página para ver as tarefas definidas no Server1 como acessíveis e sincronizadas na guia **Tarefas** do Server2.
   {:tip}
2. Passe o mouse sobre **Avançado** e selecione **Restaurar por meio de
outro computador**.
3. Na tela **Restaurar de outro computador**, faça as seleções a seguir.
  - Área segura: essa entrada é padronizada para a área segura do Server1.
  - Computador: selecione Server1 como o computador de backup do qual restaurar.
  - Tarefa: selecione a tarefa de backup de Server1.
4. Clique em **Avançar**
5. Confirme as informações de Origem
  - O **Local do conjunto de segurança** é o local de Área segura para o Server1.
  - Na seção **Selecionar uma versão de backup**, especifique seu backup do Server1 como a versão de backup.
  - A senha de criptografia é a senha que você usou quando criou o backup do Server1.
6. Clique em **Avançar**
7. Selecione quais arquivos precisam ser restaurados do backup do Server1. Marque as caixas próximas aos arquivos e diretórios que deseja restaurar e, em seguida, clique em **Incluir** para salvar suas opções.
8. Clique em **Avançar** para mover para as opções de restauração.
9. Em Opções
  - Destino: selecione **Restaurar para o local original**
  - Sobrescrição do arquivo: selecione **Sobrescrever arquivos existentes**
10. Clique em **Executar restauração**.
11. A tela Detalhe do processo exibe o status da tarefa de restauração.


## Verificando a restauração
{: #verifyrestore}

1. Conecte-se à raiz do Server2 por meio de SSH.
2. Liste os arquivos e todas as entradas de diretório em um formato longo.
  ```
  ls -la
  ```
  {: pre}

3. Compare a saída.

## Continuando o planejamento de backup normal
{: #resumeschedule}

1. Quando a restauração for concluída, remova as informações de registro do server1, por meio do qual os
dados foram restaurados.
2. Insira o registro atual do server2 e ative as tarefas de Planejamento.
