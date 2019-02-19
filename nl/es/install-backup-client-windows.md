---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-05"

---
{:pre: .pre}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Instalación del cliente de copia de seguridad en Windows
{: #InstallinWindows}

La instalación del cliente de {{site.data.keyword.backup_full}} en Windows se completa a través de una serie de interacciones en el servidor designado para el servicio de {{site.data.keyword.backup_notm}}.

Para obtener más información sobre las copias de seguridad para servidores Windows 2016, consulte [Configuración de {{site.data.keyword.backup_notm}} en Windows 2016](/docs/infrastructure/Backup?topic=Backup-InstallinWindows2016).
{:tip}

## Inicie una sesión en el servidor del dispositivo de destino

1. Inicie la sesión en la [consola de {{site.data.keyword.cloud_notm}}](https://{DomainName}/catalog/){:new_window} y pulse el icono de **menú** de la parte superior izquierda. Seleccione **Infraestructura clásica**. <br/>
   También puede iniciar la sesión en el [{{site.data.keyword.slportal}} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://control.softlayer.com/){:new_window}.
2. Seleccione **Dispositivos** > **Lista de dispositivos** en el menú principal para ver la lista de servidores disponibles.
3. Busque el dispositivo para el que ha adquirido el servicio de {{site.data.keyword.backup_notm}} y anote su dirección IP pública.
4. Pulse la flecha que apunta a la derecha para ampliar y ver más información sobre el dispositivo, incluido el nombre de usuario y la contraseña. Si no se muestra la contraseña, pulse **Mostrar contraseña** para verla.
5. Inicie una sesión en el dispositivo de destino mediante una conexión remota de escritorio.

## Descarga del cliente de copia de seguridad

1. En el servidor de destino, abra una sesión de navegador y especifique el siguiente URL para descargar el archivo ejecutable para el cliente de {{site.data.keyword.backup_notm}}. <br/>
  ```
  http://downloads.service.softlayer.com/evault/
  ```
  {:pre}

2. Efectúe una doble pulsación en el archivo descargado.
3. Pulse **Ejecutar**.


## Instalación y registro del agente de copia de seguridad

1. Escriba la dirección de red: <br />
  ```
  https://ev-webcc01.service.softlayer.com
  ```
  {: pre}

2. Especifique el nombre de usuario en el campo **Nombre de usuario**.
3. Escriba la contraseña en el campo **Contraseña**.
6. Pulse **Siguiente**
7. Para completar la instalación, pulse **Instalar**.

## Configuración de agentes de copia de seguridad

Inicie una sesión en el portal de {{site.data.keyword.backup_notm}} para configurar y gestionar los agentes de copia de seguridad. Para obtener más información, consulte la [Guía de aprendizaje Cómo empezar](docs/infrastructure/Backup?topic=Backup-GettingStarted).
