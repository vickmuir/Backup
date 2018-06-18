---

copyright:
  years: 1994, 2018
lastupdated: "2018-05-31"

---
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Copia de seguridad y restauración entre una VSI y otra con el mismo centro de datos

Es posible que desee restaurar datos en otro servidor del mismo centro de datos. Estas instrucciones le ayudarán a llevar a cabo esta tarea. Este procedimiento solo se aplica a las restauraciones a nivel de archivo de archivos que no sean del sistema operativo. Para restaurar una imagen del sistema, siga las instrucciones de [Windows BMR](restoring-evault-bmr-system-volume-image.html).

Este proceso incluye el registro del agente de EVault en el segundo servidor para que pueda acceder a la ubicación de EVault del primer servidor y la realización de la tarea **Restaurar desde otro sistema**.


## Requisitos previos

- Servidor1 y Servidor2 deben tener el mismo sistema operativo. No se da soporte a las restauraciones entre plataformas.
- Servidor1 y Servidor2 deben tener agentes de EVault configurados. Para ver cómo se configuran los agentes de EVault, pulse [aquí](index.html#configuring-evault-agent-in-webcc)
- Un trabajo de copia de seguridad para el Servidor1 ha generado una copia de seguridad en la ubicación de EVault del Servidor1.

**Nota**: inhabilite todas las tareas planificadas en ambos servidores para evitar conflictos. 

## Iniciar WebCC en el Servidor2

**Nota**: recuerde iniciar la conexión {{site.data.keyword.BluVPN}} para obtener acceso a la red privada de {{site.data.keyword.BluSoftlayer_full}}; de lo contrario, los enlaces de WebCC no funcionarán.

1. Inicie una sesión en el {{site.data.keyword.slportal}} de [](https://control.softlayer.com/){:new_window} y pulse **Almacenamiento** > **Copia de seguridad** en el menú principal para visualizar los servidores con el servicio de copia de seguridad de EVault. 
2. Seleccione Servidor2. Pulse la flecha de expansión que apunta a la derecha para visualizar el enlace WebCC.
3. Pulse **Inicio de sesión de WebCC** para iniciar el cliente WebCC en el navegador.

## Volver a registrar EVault:
1. Pulse **Todos los agentes** y abra el agente específico que desea modificar.
2. Pulse **Editar** y seleccione *Valores de almacén".
3. Pulse **Volver a registrar** para conectar el Servidor1 con el Servidor2.
4. En la pantalla **Volver a registrar almacén** correspondiente a la entrada **Utilizar un perfil de almacén**, seleccione la entrada **Especificar valores de almacén**.
5. Especifique el nombre de almacén, que coincide con el nombre de EVault de Servidor1.
6. Especifique las credenciales de Servidor1 para iniciar una sesión en el EVault de Servidor1.
7. Pulse **Cargar sistemas**; se mostrarán los servidores que están conectados a la ubicación del almacén.
8. Pulse **Guardar cambios**.
9. Cuando se le solicite, pulse **Sí** para confirmar el nuevo registro de EVault.

## Ejecutar el trabajo de copia de seguridad desde Servidor1 como un trabajo de restauración en Servidor2

1. Pulse **Todos los agentes**. <br/> **Nota**: es posible que tenga que renovar la página para ver los trabajos definidos en Servidor1 como accesibles/sincronizados en el separador **Trabajos** del Servidor 2
2. Mueva el cursor sobre **Avanzado** y seleccione **Restaurar desde otro sistema**.
3. En la pantalla **Restaurar desde otro sistema**, realice las siguientes selecciones:
  - Almacén: esta entrada debería adoptar como valor predeterminado el EVault de Servidor1
  - Sistema: seleccione el Servidor1 como sistema de copia de seguridad desde el que realizar la restauración. 
  - Trabajo: seleccione el trabajo de copia de seguridad de Servidor1.
4. Pulse **Siguiente**
5. Confirme la información de origen
  - **Ubicación del conjunto seguro** debería ser la ubicación del almacén correspondiente a Servidor1.
  - En la sección **Seleccionar una versión de copia de seguridad**, la versión de copia de seguridad especificada debería ser la copia de seguridad de Servidor1
  - La contraseña de cifrado debería ser la contraseña que ha utilizado al realizar la copia de seguridad en Servidor1.
6. Pulse **Siguiente**
7. Selección de datos: seleccione los archivos que desea restaurar de la copia de seguridad de Servidor1. Marque los recuadros de selección que hay junto a los archivos y directorios que desea incluir y luego pulse **Incluir** para guardar las selecciones.
8. Pulse **Siguiente** para pasar a las opciones de restauración.
9. Opciones de entrada:
  - Destino: seleccione **Restaurar en ubicación original**
  - Sobrescritura de archivos: seleccione **Sobrescribir archivos existentes**
10. Pulse **Ejecutar restauración**.
11. La pantalla de detalles del proceso muestra el estado del trabajo de restauración.


## Verificar la restauración

1. Conecte con root de Servidor2 mediante SSH.
2. Cree una lista de los archivos que incluya todas las entradas de directorio en un formato largo.
  ```
  ls -la
  ```
  {: pre}
  
3. Compare la información de salida.
  
## Reanudar la planificación normal de la copia de seguridad.

1. Una vez finalizada la restauración, elimine la información de registro de Servidor1, desde el que se han restaurado los datos. 
2. Especifique el registro de Servidor2 actual y habilite las tareas de planificación.
 

  

 
 
  
  
