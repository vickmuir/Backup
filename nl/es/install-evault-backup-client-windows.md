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

# Instalación del cliente de copia de seguridad de EVault en Windows

La instalación del cliente de copia de seguridad de EVault en Windows se realiza mediante una serie de interacciones con un usuario conectado al servidor designado para el servicio de copia de seguridad de EVault. Siga los pasos siguientes para instalar el cliente de copia de seguridad de EVault en Windows.

**Nota**: Windows 2016 no recibe soporte actualmente.

## Inicie una sesión en el servidor del dispositivo de destino

1. Inicie una sesión en el {{site.data.keyword.slportal}} de [](https://control.softlayer.com/){:new_window} y seleccione **Dispositivos** > **Lista de dispositivo** en el menú principal para ver los dispositivos de servidor disponibles.
2. Busque el dispositivo para el que ha adquirido el servicio de EVault y anote su dirección IP pública.
3. Pulse la flecha de expansión que apunta a la derecha para visualizar más información sobre el dispositivo, incluido el nombre de usuario y la contraseña. Si no se muestra la contraseña, pulse el recuadro de selección **Mostrar contraseña** para verla. 
4. Inicie una sesión en el dispositivo de destino mediante una conexión remota de escritorio.

## Descargue el cliente de EVault

1. En el servidor de destino, abra una sesión de navegador y especifique el siguiente URL para descargar el archivo ejecutable para el cliente de copia de seguridad de EVault. <br/>
  ```
  http://downloads.service.softlayer.com/evault/
  ```
  {:pre}
  
2. Realice una doble pulsación en el archivo descargado y pulse **Ejecutar** en el recuadro emergente que aparece.


## Instale y registre el agente de EVault
 
1. Escriba la dirección de red: <br />
  ```
  ev-webcc01.service.softlayer.com
  ```
  {: pre}
  
2. Especifique el nombre de usuario de copia de seguridad de EVault en el campo **Nombre de usuario**. 
3. Escriba la contraseña de copia de seguridad de EVault en el campo **Contraseña**. 
6. Pulse **Siguiente** 
7. Para completar la instalación, pulse **Instalar**.

## Siguientes pasos

Inicie una sesión en WebCC para configurar y gestionar los agentes de copia de seguridad. Consulte la [Guía de aprendizaje de iniciación](index.html#configuring-evault-agent-in-webcc) para ver instrucciones.
