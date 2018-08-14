---

copyright:
  years: 1994, 2018
lastupdated: "2018-06-26"

---
{:pre: .pre}
{:new_window: target="_blank"}

# Instalando o EVault Backup Client no Windows

A instalação do EVault Backup Client no Windows é concluída por meio de uma série de interações no servidor que está designado para o serviço de backup do EVault.

**Nota**: o Windows 2016 não é suportado atualmente. Consulte as instruções para o [Windows 2016](install-evault-windows2016.html)

## Efetuando login no servidor de dispositivo de destino

1. Efetue login no [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} e selecione
**Dispositivos** > **Lista de dispositivos** no menu principal para ver a lista de servidores disponíveis.
2. Localize o dispositivo para o qual você comprou o serviço do EVault e anote o seu endereço IP público.
3. Clique na seta que aponta para a direita para expandir e mostrar mais informações sobre o dispositivo, incluindo o nome do usuário e a senha. Se a senha não for exibida, clicar em **Mostrar senha** a revelará. 
4. Efetue login no dispositivo de destino usando a Conexão de Área de Trabalho Remota.

## Fazendo download do cliente do EVault

1. No servidor de destino, abra uma sessão do navegador e insira a URL a seguir para fazer download do
arquivo executável para o EVault Backup Client. <br/>
  ```
  http://downloads.service.softlayer.com/evault/
  ```
  {:pre}
  
2. Dê um clique duplo no arquivo transferido por download.
3. Clique em **Executar**.


## Instalando e registrando o EVault Agent
 
1. Insira o endereço de rede: <br />
  ```
  ev-webcc01.service.softlayer.com
  ```
  {: pre}
  
2. Insira o nome do usuário do EVault no campo **Nome do usuário**. 
3. Insira a senha do EVault no campo **Senha**. 
6. Clique em **Avançar** 
7. Clique em **Instalar** para concluir a instalação.

## Configurando os agentes de backup

Efetue login no WebCC para configurar e gerenciar seus agentes de backup. Consulte o [Tutorial de introdução](index.html#configuring-evault-agent-in-webcc) para obter instruções.
