---

copyright:
  years: 1994, 2018
lastupdated: "2018-12-14"

---
{:codeblock: .codeblock}
{:pre: .pre}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Instalación del cliente de copia de seguridad en Linux

La instalación del cliente de {{site.data.keyword.backup_full}} en un sistema operativo basado en Linux se puede realizar a través de una serie de mandatos en el shell o en el terminal dentro del sistema operativo. En este procedimiento se indican los pasos necesarios para instalar el cliente en cualquiera de los siguientes sistemas operativos basados en Linux:

- RHEL
- CentOS
- CloudLinux

Después de completar el procedimiento, el proceso automatizado registra el servicio del agente con el portal de {{site.data.keyword.backup_notm}} y luego descarga e instala los archivos necesarios para ejecutar el servicio.

Si ha adquirido {{site.data.keyword.backup_notm}} cuando ha solicitado un servidor a través del [catálogo de {{site.data.keyword.cloud_notm}}](https://{DomainName}/catalog/){:new_window} o el {{site.data.keyword.slportal}}, el software se instala automáticamente. No es necesario que siga los procedimientos que se describen en este documento.
{:tip}

Si ha adquirido {{site.data.keyword.backup_notm}} como una actualización en el {{site.data.keyword.slportal}}, siga estos pasos para instalar el software.

## Inicie una sesión en el servidor del dispositivo de destino

1. Inicie una sesión en la [consola de {{site.data.keyword.cloud_notm}}](https://{DomainName}/){:new_window} y pulse el icono de **menú** de la parte superior izquierda. Seleccione **Infraestructura clásica**.<br/>
   También puede iniciar la sesión en [{{site.data.keyword.slportal}} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://control.softlayer.com/){:new_window}.
2. Seleccione **Dispositivos** > **Lista de dispositivos** en el menú principal para ver la lista de dispositivos de servidor disponibles.
3. Busque el dispositivo para el que ha adquirido el servicio de {{site.data.keyword.backup_notm}} y anote su dirección IP pública.
  - Esta dirección IP se utilizará en los siguientes pasos cuando se inicie una sesión en el dispositivo desde una línea de mandatos de UNIX o Linux. Sustituya <direcciónIPPública> por la dirección IP pública real en el mandato del Paso 5.
4. Pulse la flecha que apunta a la derecha para visualizar más información sobre el dispositivo, incluido el nombre de usuario y la contraseña.
  - Si no se muestra la contraseña, pulse **Mostrar contraseña** para verla. El nombre de usuario y la contraseña se utilizan en el paso siguiente para iniciar una sesión en el dispositivo de prueba. Sustituya `<user name>` por el nombre de usuario real.
5. Inicie una sesión en el dispositivo de destino el siguiente mandato desde una línea de mandatos de UNIX o Linux.
   ```
   ssh <nombre usuario>@<direcciónIPPública>
   ```
   {: pre}

   Si nunca ha iniciado una sesión en este servidor con este nombre de usuario, aparecerá un mensaje con información sobre la autenticidad del host. También se le preguntará si desea continuar. Responda **sí** para continuar.
   {:note}

6. Se le solicitará que especifique la contraseña, a menos que antes haya configurado claves ssh para acceder a este servidor.

## Actualización del sistema operativo para preparar la instalación (sólo RHEL)

Este paso es obligatorio para RHEL, pero opcional para otras distribuciones de Linux.
{:tip}

- Ejecute el mandato siguiente en el indicador del servidor.
  ```
  yum update
  ```
  {: pre}

  Si se le solicita, confirme que el tamaño de descarga es correcto. La actualización continúa y muestra el mensaje "Completado" cuando termina.

## Obtención del script de instalación

- Ejecute el mandato siguiente en el indicador del servidor.
  ```
  wget -N http://downloads.service.softlayer.com/evault/evault_manual.sh
  ```
  {: pre}

## Ejecución del script de instalación

1. Ejecute el mandato siguiente en el indicador del servidor.
   ```
   sh ./evault_manual.sh
   ```
   {: pre}

2. Escriba su nombre de usuario y contraseña en el portal de {{site.data.keyword.backup_notm}}.

   Para obtener más información sobre cómo visualizar el nombre de usuario y la contraseña de {{site.data.keyword.backup_notm}}, consulte [Cómo empezar con los servicios de copia de seguridad](index.html#accessing-and-viewing-ibm-cloud-backup-storage-details).
   {:tip}

3. Después del nombre de usuario y de la contraseña, no se necesita ninguna otra información de entrada. Las solicitudes que aparecerán en pantalla a medida que progresa la instalación pueden ignorarse sin problemas.

   Las genera un subscript iniciado por el script `evault_manual.sh`. El script `evault_manual.sh` genera la entrada para estas solicitudes.
   {:note}

4. La instalación está completa cuando aparecen los mensajes siguientes:

   ```
   Starting VVAgent: [  OK  ]
   Starting buagent: [  OK  ]
   ```
   {: codeblock}

## Verificación de que la instalación se ha realizado correctamente

1. Verifique que aparece el mensaje "Registrado en el portal" en la información de salida de la instalación. Para ello, busque el mensaje en la pantalla o examine la información de salida del siguiente mandato:
   ```
   grep 'Registered'  /opt/BUAgent/Install.log
   ```
   {: pre}

2. Ejecute el mandato siguiente y examine la información de salida.
   ```
   service vvagent status
   ```
   {: pre}

   Se muestran los mensajes siguientes.
   ```
   VVAgent is running (PID xxxxx).
   buagent is running (PID xxxxx).
   ```
   {: codeblock}

  Los ID de proceso representados por `xxxxx` varían con cada instalación.
  {:tip}

**Siguientes pasos**

Inicie una sesión en el portal de {{site.data.keyword.backup_notm}} para configurar y gestionar los agentes de copia de seguridad. Para obtener más información, consulte la [Guía de aprendizaje Cómo empezar](index.html#configuring-the-backup-agent-and-the-backup-schedule) y [Configuración de una copia de seguridad simple a nivel de archivo en Linux](configure-simple-file-backup-linux.html).
