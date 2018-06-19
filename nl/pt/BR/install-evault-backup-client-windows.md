---

copyright:
  years: 1994, 2018
lastupdated: "2018-05-14"

---
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Instalando o EVault Backup Client no Windows

A instalação do EVault Backup Client no Windows é concluída por meio de uma série de interações
enquanto estiver com login efetuado no servidor designado para o serviço EVault Backup. Siga as etapas
abaixo para instalar o EVault Backup Client no Windows.

**Nota**: Windows 2016 não é suportada atualmente.

## Efetue login no servidor de dispositivo de destino

1. Efetue login no [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} e selecione **Dispositivos** > **Lista de dispositivos** no menu principal para ver a lista de dispositivos do servidor disponíveis.
2. Localize o dispositivo para o qual você comprou o serviço do EVault e anote o seu endereço IP público.
3. Clique na seta de expansão apontada para a direita para revelar mais informações sobre o
dispositivo, incluindo o nome do usuário e a senha. Se a senha não for exibida, clicar na caixa de seleção
**Mostrar senha** vai revelá-la.  
4. Efetue login no dispositivo de destino usando a Conexão de área de trabalho remota.

## Faça do Cliente EVault

1. No servidor de destino, abra uma sessão do navegador e insira a URL a seguir para fazer download do
arquivo executável para o EVault Backup Client. <br/>
  ```
  Http://downloads.service.softlayer.com/evault/
  ```
  {:pre}
  
2. Clique duas vezes no arquivo transferido por download e clique em **Executar** na caixa pop-up que aparece.


## Instalar e Registrar o Agente do EVault
 
1. Insira o endereço de rede: <br />
  ```
  Ev-webcc01.service.softlayer.com
  ```
  {: pre}
  
2. Insira o nome de usuário do EVault Backup no campo **Nome**. 
3. Insira a senha do EVault Backup no campo **Senha**. 
6. Clique em **Avançar** 
7. Clique em **Instalar** para concluir a instalação.

## Etapas Seguintes

Efetue login no WebCC para configurar e gerenciar os seus agentes de backup. Consulte o [Tutorial de Introdução](index.html#configuring-evault-agent-in-webcc) para obter instruções.
