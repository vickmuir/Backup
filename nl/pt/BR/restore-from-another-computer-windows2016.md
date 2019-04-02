---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-05"

keywords: IBM Cloud backup, EVault, Carbonite, backup, restore

subcollection: Backup

---

# Restaurando uma tarefa por meio de outro computador no Windows 2016
{: #restorefromother2016}

Use estas etapas para concluir uma restauração de arquivo de outro computador usando o Controle central do Windows.

1. Realize o controle remoto de seu servidor Windows 2016 por meio do RDP.
2. Abra o CentralControl.
3. Clique com o botão direito em **Agente** e clique em **Configuração do agente**.
4. Remova as configurações atuais da Área segura do CentralControl selecionando a entrada e clicando em
**Excluir**.
5. Clique em **Novo** e, na próxima tela, selecione **Registrar novamente o computador registrado anteriormente**. Clique em **Avançar**.
6. Insira o endereço de rede e clique em **Incluir** e, em seguida, clique em **Avançar**.
7. Insira os novos valores de porta e clique em **Incluir** e, em seguida, em **Avançar**.
8. Na tela Configurações de conexão, insira o número de segundos/minutos que você deseja.
9. Na tela Autenticação, insira suas credenciais e clique em **Avançar**.
10. A janela Computadores registrados exibe o nome do host de seu servidor. Clique em **Avançar**.
11.	Quando o assistente de configuração de área segura concluir a coleta das informações, clique em
**Concluir** para concluir o registro.
12. Quando solicitado, confirme que você deseja continuar com o novo registro.
13. Quando o registro for concluído, clique em **Restaurar** na barra de menus.
9.	Selecione o conjunto de segurança apropriado e insira a senha de criptografia. Clique em **Avançar**.
10.	Selecione os arquivos que você deseja restaurar, selecione as opções padrão e clique em **Concluir**.
11.	Quando a restauração estiver completa, remova o registro de área segura e registre novamente com as informações da conta da área segura atual.
