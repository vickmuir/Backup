---

copyright:
  years: 1994, 2018
lastupdated: "2018-12-14"

---
{:pre: .pre}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Restauración de datos entre una VSI y otra en otro centro de datos

Es posible que desee restaurar datos en otro servidor. Este procedimiento solo se aplica a las restauraciones a nivel de archivo de archivos que no son de sistema operativo. Para restaurar una imagen del sistema, siga las instrucciones de [Windows BMR](restore-bmr-system-volume-image.html).

El proceso incluye el registro del agente de copia de seguridad en el segundo servidor para que pueda acceder a la ubicación de la caja fuerte del primer servidor y la realización de la tarea **Restaurar desde otro sistema**.

**Requisitos previos**

- Servidor1 y Servidor2 deben tener el mismo sistema operativo. No se da soporte a las restauraciones entre plataformas.
- Servidor1 y Servidor2 deben tener agentes de copia de seguridad que se hayan configurado anteriormente. Para obtener más información sobre cómo configurar los agentes de copia de seguridad, consulte [Configuración del agente de copia de seguridad en el portal de {{site.data.keyword.backup_notm}}](index.html#configuring-the-backup-agent-in-webcc).
- Un trabajo de copia de seguridad para el Servidor1 que ha generado una copia de seguridad en la ubicación de la caja fuerte del Servidor1.

Inhabilite todas las tareas planificadas en ambos servidores para evitar conflictos.
{:important}

## Inicio del portal de {{site.data.keyword.backup_notm}} de Servidor2

Recuerde iniciar la conexión {{site.data.keyword.BluVPN}} para obtener acceso a la red privada de {{site.data.keyword.BluSoftlayer_full}}; de lo contrario, el enlace del portal de {{site.data.keyword.backup_notm}} no funciona.
{:tip}

1. Inicie una sesión en la [consola de {{site.data.keyword.cloud_notm}}](https://{DomainName}/catalog/){:new_window} y pulse el icono **Menú** de la parte superior izquierda. Seleccione **Infraestructura clásica**.

   También puede iniciar la sesión en [{{site.data.keyword.slportal}} ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://control.softlayer.com/){:new_window} 
2. Haga clic en **Almacenamiento** > **Copia de seguridad** para visualizar los servidores con servicio de copia de seguridad.
3. Seleccione Servidor2. Pulse la flecha de expansión hacia la derecha para revelar el enlace del portal {{site.data.keyword.backup_notm}}.
4. Pulse el **inicio de sesión en el portal de {{site.data.keyword.backup_notm}}** para iniciar el cliente del portal de {{site.data.keyword.backup_notm}} en su navegador.

## Volver a registrar la caja fuerte

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

1. Pulse **Todos los agentes**.

   Es posible que tenga que renovar la página para ver los trabajos definidos en Servidor1 como accesibles/sincronizados en el separador **Trabajos** del Servidor2.
   {:tip}
2. Mueva el cursor sobre **Avanzado** y seleccione **Restaurar desde otro sistema**.
3. En la pantalla **Restaurar desde otro sistema**, pulse **Añadir**. Los campos contienen valores predeterminados, por lo que debe modificarlos.
4. Pulse el campo Caja fuerte, seleccione **Especificar valores de caja fuerte** y escriba la dirección IP de la caja fuerte lmacén de Servidor1. Pulse **Añadir**.
5. Actualice las credenciales con las credenciales de Servidor1.
6. Pulse **Guardar cambios**. Esta acción le conecta con la caja fuerte de Servidor1.
7. En la pantalla **Restaurar desde otro sistema**, actualice los campos Sistema y Trabajo.
  - Sistema: seleccione el Servidor1 como sistema de copia de seguridad desde el que realizar la restauración.
  - Trabajo: seleccione el trabajo de copia de seguridad de Servidor1.
8. Pulse **Siguiente** para iniciar el proceso de restauración en el Servidor2 en otro centro de datos.
9. En la solicitud, especifique la contraseña de copia de seguridad y pulse **Siguiente**.
10. Confirme que se ha seleccionado el trabajo de copia de seguridad adecuado y pulse **Siguiente**. Ahora el trabajo de restauración está configurado en Servidor2.
11. Seleccione el trabajo que acaba de configurar y pulse **Ejecutar restauración**.
12. Seleccione los archivos que desea restaurar.
13. Pulse el signo más para ampliar la selección de archivos.
14. Marque el recuadro de selección de los archivos o carpetas individuales que desea restaurar de Servidor1 y de Servidor2. A continuación, pulse **Incluir**.
15. Los archivos aparecen en la ventana Conjunto de copia de seguridad de la derecha. Pulse **Siguiente**.
16. Cuando haya completado la selección de datos, continúe para seleccionar las opciones.
    - Seleccione **Restaurar en la ubicación original**.
    - Seleccione **Sobrescribir archivos existentes**.
17. Pulse **Ejecutar restauración**. La ventana Detalles del proceso muestra el estado del trabajo de copia de seguridad en ejecución. Cuando finalice la copia de seguridad, pulse **Cerrar**.


## Verificación de la restauración

1. Conecte con root de Servidor2 mediante SSH.
2. Cree una lista de los archivos y de todos los directorios en un formato largo.
  ```
  ls -la
  ```
  {: pre}

3. Compare la información de salida.

## Reanudación de una planificación normal de copia de seguridad.

1. Una vez finalizada la restauración, elimine la información de registro de Servidor1, desde el que se han restaurado los datos.
2. Especifique el registro de Servidor2 actual y habilite las tareas de planificación.
