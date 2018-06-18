---

copyright:
  years: 1994, 2018
lastupdated: "2018-05-16"

---
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Restaurar una copia de seguridad

Este artículo contiene los pasos necesarios para realizar una restauración de archivos mediante EVault. Para restaurar una imagen del sistema, siga las instrucciones de [Windows BMR](restoring-evault-bmr-system-volume-image.html).

## Iniciar WebCC

**Nota**: recuerde iniciar la conexión {{site.data.keyword.BluVPN}} para obtener acceso a la red privada de {{site.data.keyword.BluSoftlayer_full}}; de lo contrario, el enlace WebCC no funcionará.

1. Inicie una sesión en el {{site.data.keyword.slportal}} de [](https://control.softlayer.com/){:new_window} y pulse **Almacenamiento** > **Copia de seguridad** en el menú principal para visualizar los servidores con el servicio de copia de seguridad de EVault. 
2. Seleccione el servidor donde residen los archivos que desea restaurar. Pulse la flecha para visualizar el enlace WebCC.
3. Pulse **WebCC** para iniciar el cliente WebCC en el navegador. 

## Realizar la restauración

1. En el panel de navegación de la izquierda, pulse **Todos los agentes**
2. Pulse el agente para mostrar los trabajos.
3. Pulse el trabajo que contiene la copia de seguridad que desee.
4. Pulse **Ejecutar restauración**.
5. Seleccione un origen de la restauración.
6. Seleccione **Restaurar desde un solo conjunto seguro** o **Restaurar desde el conjunto más seguro especificado en el recuadro de texto siguiente**. Ambas opciones tienen el mismo efecto.
7. Seleccione una versión de copia de seguridad o especifique el número del conjunto seguro (el número del conjunto seguro es el primer número en la selección desplegable)
8. Especifique la contraseña de cifrado.
9. Pulse **Siguiente** para continuar.
10. Marque los recuadros de selección que hay junto a los archivos y directorios que desea incluir y luego pulse **Incluir** para guardar las selecciones.
11. Puede filtrar sus selecciones utilizando la pantalla emergente que aparece o pulsar **Aceptar** para utilizar las selecciones que ha realizado tal como están. <br/>
Después de haber incluido las selecciones de archivos y directorios, los archivos ya no se pueden seleccionar en el panel **Archivos de datos**. Se muestran en el panel **Conjunto de copia de seguridad** en la parte derecha de la pantalla. Puede repetir el paso 101 para añadir más archivos o para eliminar archivos que haya incluido (mediante **Excluir**). También puede utilizar la opción **Eliminar** para suprimir cualquier elemento de línea del panel **Conjunto de copia de seguridad**. Cuando esté satisfecho con la configuración del conjunto de copia de seguridad, pulse **Siguiente** para continuar.
12. Deje los valores predeterminados del panel siguiente o personalice la restauración según sus preferencias; luego pulse **Ejecutar restauración**. 
13. Los archivos se habrán restaurado por completo cuando el estado sea **Restauración completada** en la pantalla **Detalles del proceso**.
