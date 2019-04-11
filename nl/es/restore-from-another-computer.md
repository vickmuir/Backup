---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-05"

keywords: IBM Cloud backup,  EVault, Carbonite, backup, restore

subcollection: Backup

---
{:pre: .pre}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Restauración de datos entre una VSI y otra dentro del mismo centro de datos
{: #restorefromotherVSI}

Es posible que desee restaurar datos en otro servidor del mismo centro de datos. Este procedimiento solo se aplica a las restauraciones a nivel de archivo de archivos que no son de sistema operativo. Para restaurar una imagen del sistema, siga las instrucciones de [Windows BMR](/docs/infrastructure/Backup?topic=Backup-restoreBMR).

El proceso incluye el registro del agente de copia de seguridad en el segundo servidor para que pueda acceder a la ubicación de la caja fuerte del primer servidor y la realización de la tarea **Restaurar desde otro sistema**.

**Requisitos previos**

- Servidor1 y Servidor2 deben tener el mismo sistema operativo. No se da soporte a las restauraciones entre plataformas.
- Servidor1 y Servidor2 deben tener agentes de copia de seguridad que se hayan configurado anteriormente. Para obtener más información sobre cómo configurar los agentes de copia de seguridad, consulte [Configuración del agente de copia de seguridad en el portal de {{site.data.keyword.backup_notm}}](/docs/infrastructure/Backup?topic=Backup-getting-started#getting-started).
- Un trabajo de copia de seguridad para el Servidor1 que ha generado una copia de seguridad en la ubicación de la caja fuerte del Servidor1.

Inhabilite todas las tareas planificadas en ambos servidores para evitar conflictos.
{:important}

## Inicio del portal de {{site.data.keyword.backup_notm}} de Servidor2
{: #startWebCC}

Recuerde iniciar la conexión {{site.data.keyword.BluVPN}} para obtener acceso a la red privada de {{site.data.keyword.BluSoftlayer_full}}; de lo contrario, el enlace del portal de {{site.data.keyword.backup_notm}} no funciona.
{:tip}

1. Inicie la sesión en la [consola de {{site.data.keyword.cloud_notm}}](https://{DomainName}){:new_window} y pulse el icono de **menú** de la parte superior izquierda. Seleccione **Infraestructura clásica**. <br/>
   También puede iniciar la sesión en el [{{site.data.keyword.slportal}} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://control.softlayer.com/){:new_window}.
2. Pulse **Almacenamiento** > **Copia de seguridad** para visualizar los servidores con servicio de copia de seguridad.
3. Seleccione Servidor2. Pulse la flecha de expansión hacia la derecha para revelar el enlace del portal de {{site.data.keyword.backup_notm}}.
4. Pulse el **inicio de sesión en el portal de {{site.data.keyword.backup_notm}}** para iniciar el cliente del portal en su navegador.

## Volver a registrar la caja fuerte
{: #reregistervault}

1. Pulse **Todos los agentes** y abra el agente específico que desea modificar.
2. Pulse **Editar** y seleccione **Valores de caja fuerte**.
3. Pulse **Volver a registrar** para conectar el Servidor1 con el Servidor2.
4. En la pantalla **Volver a registrar caja fuerte** correspondiente a la entrada **Utilizar un perfil de caja fuerte**, seleccione **Especificar valores de caja fuerte**.
5. Especifique el nombre de almacenamiento, que es el mismo que el nombre de la caja fuerte del Servidor1.
6. Especifique las credenciales del Servidor1 para iniciar una sesión en la caja fuerte del Servidor1.
7. Pulse **Cargar sistemas**; se mostrarán los servidores que están conectados a la ubicación de la caja fuerte.
8. Pulse **Guardar cambios**.
9. Cuando se le solicite, pulse **Sí** para confirmar el nuevo registro de caja fuerte.

## Ejecución del trabajo de copia de seguridad de Servidor1 como un trabajo de restauración en Servidor2
{: #runbackuprestore}

1. Pulse **Todos los agentes**.

   Es posible que tenga que renovar la página para ver los trabajos definidos en Servidor1 como accesibles y sincronizados en el separador **Trabajos** del Servidor2.
   {:tip}
2. Mueva el cursor sobre **Avanzado** y seleccione **Restaurar desde otro sistema**.
3. En la pantalla **Restaurar desde otro sistema**, realice las siguientes selecciones.
  - Caja fuerte: esta entrada adopta como valor predeterminado la caja fuerte del Servidor1.
  - Sistema: seleccione el Servidor1 como sistema de copia de seguridad desde el que realizar la restauración.
  - Trabajo: seleccione el trabajo de copia de seguridad de Servidor1.
4. Pulse **Siguiente**
5. Confirme la información de origen
  - **Ubicación del conjunto seguro** es la ubicación de la caja fuerte correspondiente a Servidor1.
  - En la sección **Seleccionar una versión de copia de seguridad**, especifique la copia de seguridad de Servidor1 como versión de copia de seguridad.
  - La contraseña de cifrado es la contraseña que ha utilizado al crear la copia de seguridad de Servidor1.
6. Pulse **Siguiente**
7. Seleccione los archivos que desea restaurar de la copia de seguridad de Servidor1. Marque los recuadros de selección que hay junto a los archivos y directorios que desea restaurar y luego pulse **Incluir** para guardar las selecciones.
8. Pulse **Siguiente** para pasar a las opciones de restauración.
9. Opciones de entrada
  - Destino: seleccione **Restaurar en ubicación original**
  - Sobrescritura de archivos: seleccione **Sobrescribir archivos existentes**
10. Pulse **Ejecutar restauración**.
11. La pantalla de detalles del proceso muestra el estado del trabajo de restauración.


## Verificación de la restauración
{: #verifyrestore}

1. Conecte con root de Servidor2 mediante SSH.
2. Cree una lista de los archivos y de todos los directorios en un formato largo.
  ```
  ls -la
  ```
  {: pre}

3. Compare la información de salida.

## Reanudación de una planificación normal de copia de seguridad.
{: #resumeschedule}

1. Una vez finalizada la restauración, elimine la información de registro de Servidor1, desde el que se han restaurado los datos.
2. Especifique el registro de Servidor2 actual y habilite las tareas de planificación.
