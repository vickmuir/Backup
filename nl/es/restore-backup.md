---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-05"

keywords: IBM Cloud backup, EVault, Carbonite, backup, restore

subcollection: Backup

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Restauración a partir de una copia de seguridad
{: #simplerestore}

Siga estos pasos para completar una restauración de archivos con {{site.data.keyword.backup_full}}. Para restaurar una imagen del sistema, siga las instrucciones de [Windows BMR](/docs/infrastructure/Backup?topic=Backup-restoreBMR#restoreBMR).

## Inicio del portal de {{site.data.keyword.backup_notm}}
{: #startWebCCsimple}

Recuerde iniciar la conexión {{site.data.keyword.BluVPN}} para obtener acceso a la red privada de {{site.data.keyword.BluSoftlayer_full}}. De lo contrario, el enlace del portal de {{site.data.keyword.backup_notm}} no funciona.
{:important}

1. Inicie la sesión en la [consola de {{site.data.keyword.cloud_notm}}](https://{DomainName}){:new_window} y pulse el icono de **menú** de la parte superior izquierda. Seleccione **Infraestructura clásica**. <br/>
   También puede iniciar la sesión en el [{{site.data.keyword.slportal}} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://control.softlayer.com/){:new_window}.
2. Pulse **Almacenamiento** > **Copia de seguridad** para visualizar los servidores con servicio de copia de seguridad.
3. Seleccione el servidor donde se encuentran los archivos que se van a restaurar. Pulse la flecha para revelar el enlace del portal de {{site.data.keyword.backup_notm}}.
4. Pulse **portal de {{site.data.keyword.backup_notm}}** para iniciar el cliente del portal de {{site.data.keyword.backup_notm}} en su navegador.

## Restauración de datos

1. En el panel de navegación de la izquierda, pulse **Todos los agentes**.
2. Pulse el agente para mostrar los trabajos.
3. Pulse el trabajo que contiene los datos que desea.
4. Pulse **Ejecutar restauración**.
5. Seleccione el origen de la restauración.
6. Seleccione la versión de copia de seguridad.
7. Escriba la contraseña de cifrado.
8. Pulse **Siguiente** para continuar.
9. Marque los recuadros de selección que hay junto a los archivos y directorios que desea incluir. A continuación, pulse **Incluir** para guardar sus opciones.
10. Puede filtrar más sus selecciones utilizando la ventana que aparece o puede pulsar **Aceptar** para utilizar las selecciones que ha realizado tal como están.
Después de haber incluido las selecciones de archivos y directorios, los archivos ya no se pueden seleccionar en el panel de archivos de datos. Se muestran en el panel del conjunto de copia de seguridad a la derecha.

   Puede repetir el paso 10 para añadir más archivos o para eliminar archivos que ha añadido anteriormente (con la opción **Excluir**). También puede utilizar la opción **Eliminar** para suprimir cualquier elemento de línea del panel **Conjunto de copia de seguridad**.
   {:tip}

11. Cuando esté satisfecho con la configuración del conjunto de copia de seguridad, pulse **Siguiente** para continuar.
12. Deje los valores predeterminados del panel siguiente o personalice la restauración según sus preferencias. A continuación pulse **Ejecutar restauración**.
13. Los archivos se habrán restaurado cuando el estado sea **Restauración completada** en la pantalla **Detalles del proceso**.
