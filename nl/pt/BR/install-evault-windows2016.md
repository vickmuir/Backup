---

copyright:
  years: 1994, 2018
lastupdated: "2018-06-05"

---
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Configurar EVault no Windows 2016

Atualmente, o EVault WebCC não é suportado oficialmente no Windows 2016. Os servidores que estão em
execução no Windows 2016 devem usar o software Windows Central Control.

## Instalando o agente de backup do EVault

1. No servidor de destino, abra uma sessão do navegador e insira a URL a seguir para fazer download do
arquivo executável
   ```
   Http://downloads.service.softlayer.com/evault/
   ```
   {:pre}
2. Clique duas vezes no arquivo transferido por download e clique em **Executar** na caixa pop-up que aparece.
3. Selecione seu idioma para a instalação e clique em **OK**.
4. Selecione **Típica** para o Tipo de configuração. Clique em **Avançar**.
5. Na tela Registrar o agente com o portal, selecione **Ignorar registro**. 
6. Clique em **Avançar**, em seguida, clique em **Concluir**.

## Instalando o CentralControl Software EVault

1. No servidor de destino, abra uma sessão do navegador e insira a URL a seguir para fazer download do
arquivo executável.

   ```
   Http://downloads.service.softlayer.com/evault/CentralControl/
   ```
   {:pre}

2. Clique duas vezes no arquivo transferido por download e clique em **Executar** na caixa pop-up que aparece.
3. Siga as etapas de instalação para uma configuração Típica.

## Configurando o CentralControl

Essa tarefa é concluída por meio de uma série de interações enquanto estiver com login efetuado no
servidor designado para o serviço EVault Backup.

1. Controle remoto seu servidor através de RDP.
2. Iniciar CentralControl.
3. Na área de trabalho, clique com o botão direito em **Agente** e selecione
**Configuração do agente**.
4. Clique em **Novo**.
5. Selecione **Registrar como um novo computador** e clique em
**Avançar**.
6. Insira o endereço de rede e clique em **Incluir** e, em seguida, clique em **Avançar**.
7. Insira os novos valores de porta e clique em **Incluir** e, em seguida, em **Avançar**.
8. Na tela Configurações de conexão, insira o número de segundos/minutos que você deseja. 
9. Na tela de autenticação, insira as suas credenciais e clique em **Avançar**.
10. A janela Computadores registrados exibe o nome do host de seu servidor. Clique em **Avançar**.
11.	O Assistente de configuração de área segura terminou de coletar as suas informações; clique em **Concluir** para concluir o registro.


