---

copyright:
  years: 1994, 2018
lastupdated: "2018-12-14"

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Restauración desde una copia de seguridad

Siga estos pasos para completar una restauración de archivos con {{site.data.keyword.backup_full}}. Para restaurar una imagen del sistema, siga las instrucciones de [Windows BMR](restore-bmr-system-volume-image.html).

## Inicio de WebCC

Recuerde iniciar la conexión {{site.data.keyword.BluVPN}} para obtener acceso a la red privada de {{site.data.keyword.BluSoftlayer_full}}. De lo contrario, el enlace WebCC no funciona.
{:important}

1. Inicie una sesión en la [consola de {{site.data.keyword.cloud_notm}}](https://{DomainName}/catalog/){:new_window} y pulse el icono **Menú** de la parte superior izquierda. Seleccione **Infraestructura clásica**.

   También puede iniciar la sesión en el [{{site.data.keyword.slportal}} ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://control.softlayer.com/){:new_window}.
2. Haga clic en **Almacenamiento** > **Copia de seguridad** para visualizar los servidores con servicio de copia de seguridad.
3. Seleccione el servidor donde se encuentran los archivos que se van a restaurar. Pulse la flecha para visualizar el enlace WebCC.
4. Pulse **WebCC** para iniciar el cliente WebCC en el navegador.

## Restauración de datos

1. En el panel de navegación de la izquierda, pulse **Todos los agentes**.
2. Pulse el agente para mostrar los trabajos.
3. Pulse el trabajo que contiene la copia de seguridad que desee.
4. Pulse **Ejecutar restauración**.
5. Seleccione un origen de la restauración.
6. Seleccione una versión de copia de seguridad.
7. Escriba la contraseña de cifrado.
8. Pulse **Siguiente** para continuar.
9. Marque los recuadros de selección que hay junto a los archivos y directorios que desea incluir y luego pulse **Incluir** para guardar las selecciones.
10. Puede filtrar más sus selecciones utilizando la ventana que aparece o puede pulsar **Aceptar** para utilizar las selecciones que ha realizado tal como están.
Después de haber incluido las selecciones de archivos y directorios, los archivos ya no se pueden seleccionar en el panel **Archivos de datos**. Se muestran en el panel **Conjunto de copia de seguridad** a la derecha.

   Puede repetir el paso 10 para añadir más archivos o para eliminar archivos que ha añadido anteriormente (con la opción **Excluir**). También puede utilizar la opción **Eliminar** para suprimir cualquier elemento de línea del panel **Conjunto de copia de seguridad**.
   {:tip}
11. Cuando esté satisfecho con la configuración del conjunto de copia de seguridad, pulse **Siguiente** para continuar.
12. Deje los valores predeterminados del panel siguiente o personalice la restauración según sus preferencias; luego pulse **Ejecutar restauración**.
13. Los archivos se habrán restaurado cuando el estado sea **Restauración completada** en la pantalla **Detalles del proceso**.
