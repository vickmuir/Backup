---

copyright:
  years: 1994, 2019
lastupdated: "2019-04-01"

keywords: IBM Cloud Backup, VMware, VRA, vSphere Recovery Agent, plug-in, plugin, EVault, Carbonite, vSphere

subcollection: Backup

---
{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Configuración de trabajos de copia de seguridad VRA
{: #ConfigureVRA}

Una vez que ha añadido el entorno VMware vSphere  en el portal de {{site.data.keyword.backup_notm}}, puede crear un trabajo de copia de seguridad que especifique las máquinas virtuales (VM) de las que hay que hacer copia de seguridad y dónde guardar los datos de copia de seguridad. Para hacer copia de seguridad de los datos, puede ejecutar el trabajo de copia de seguridad manualmente o planificar su ejecución.

Debe configurar los Valores de caja fuerte y la información del vCenter para poder añadir un trabajo de copia de seguridad.
{:important}

## Inicio del portal de {{site.data.keyword.backup_notm}}
{: #startWebCCVRA}

Debe estar conectado a la red privada de {{site.data.keyword.BluSoftlayer_full}} para poder iniciar el portal de {{site.data.keyword.backup_notm}}.
{:important}

1. Inicie la sesión en la [consola de {{site.data.keyword.cloud_notm}}](https://{DomainName}){: external} y pulse el icono de **menú** de la parte superior izquierda. Seleccione **Infraestructura clásica**. <br/>
   También puede iniciar la sesión en el [{{site.data.keyword.slportal}}](https://control.softlayer.com/){: external}.
2. Pulse en **Almacenamiento** > **Copia de seguridad** para visualizar los servidores con servicios de copia de seguridad.
3. Seleccione el servidor donde se encuentran los archivos de los que va a hacer copia de seguridad. Pulse la flecha de expansión hacia la derecha para revelar el enlace del portal de {{site.data.keyword.backup_notm}}.
4. Pulse el **inicio de sesión en el portal de {{site.data.keyword.backup_notm}}** para iniciar el cliente del portal en su navegador.

   Si el portal de {{site.data.keyword.backup_notm}} no se inicia, es posible que tenga un problema con la conexión VPN. También puede ver un mensaje que indique que el método de envío no es seguro. Esto es normal; continúe con el envío del formulario.
   {:tip}

## Añadir un trabajo de copia de seguridad de vSphere

1. En la navegación, pulse **Sistemas**. En la página Sistemas de muestran los sistemas y entornos registrados.
2. Pulse **Trabajos**.
3. En el menú de Tarea, Seleccionar trabajo, pulse **Crear nuevo trabajo VMware vCenter**.
4. Especifique la información siguiente.
   * En el campo **Nombre**, escriba un nombre para el trabajo de copia de seguridad.
   * En el campo **Descripción**, escriba, opcionalmente una descripción del trabajo de copia de seguridad.
   * En la lista **Destino**, seleccione la caja fuerte donde desea guardar los datos de copia de seguridad.
   * En los campos **Contraseña** y **Confirmar contraseña**, escriba una contraseña de cifrado. También puede escribir una ayuda para la contraseña en el campo Ayuda para la contraseña.
   Una caja fuerte solo aparece en la lista si está asignada al usuario, o si el usuario la ha añadido en los Valores de caja fuerte del sistema.<br/>
   Para los nuevos trabajos de copia de seguridad, el método de cifrado es AES de 256 bits. Los trabajos existentes pueden tener otros métodos de cifrado.
   {:note}

5.	En el campo **Incluir en la copia de seguridad**, lleve a cabo uno o más de los pasos siguientes hasta que en el campo Conjunto de copia de seguridad se muestren las VM que desea incluir en el trabajo de copia de seguridad.

   * Para añadir unas VM específicas al trabajo de copia de seguridad, seleccione cada una de ellas y pulse **Incluir**.
   * Para excluir algunas VM específicas del trabajo de copia de seguridad, seleccione cada una de ellas y pulse **Excluir**.
   * Para añadir algunas VM al trabajo de copia de seguridad por su nombre, marque el recuadro Máquinas virtuales y pulse **Incluir**.
   * Para eliminar un registro de inclusión o exclusión del recuadro Conjunto de copia de seguridad, pulse **Suprimir** junto al registro.

6. Pulse **Aplicar ahora** para consolidar y simplificar los registros del recuadro Conjunto de copia de seguridad, si es necesario aplicar cambios.
7. Pulse **Crear trabajo**.

## Configurar una planificación

Una vez que se ha creado el trabajo de copia de seguridad, puede añadir una o más planificaciones para ejecutar el trabajo automáticamente.

1. Al pulsar **Crear trabajo**, aparece la ventana de planificación y ofrece la opción de configurar una planificación personalizada para el trabajo de copia de seguridad.

   De forma predeterminada, está seleccionado retención diaria para el trabajo. En esta ventana, se puede modificar Retención y Planificación del trabajo, y también se pueden asignar varios esquemas de retención al trabajo de copia de seguridad.
   {:note}
2. Pulse **Guardar** para guardar la nueva planificación. El nuevo trabajo aparece en el separador Sistemas, en la sección Trabajos. En Estado de última copia de seguridad se puede ver que el trabajo no se ha ejecutado nunca. El trabajo de copia de seguridad planificado se ejecutará automáticamente a la hora planificada.

## Ejecución de un trabajo planificado

Los trabajos de copia de seguridad planificados también se pueden ejecutar inmediatamente.

1. Pulse **Seleccionar acción** y seleccione **Ejecutar trabajo**. Aparecerá la ventana Ejecutar trabajo con información sobre la Caja fuerte de destino y el Esquema de retención que están asignados al trabajo.

   Si el trabajo tiene asignados varias cajas fuertes al trabajo, se pueden cambiar las opciones en la ventana Ejecutar trabajo pulsando en las opciones de menú Destino y Esquema de retención.
   {:note}
2. Pulse **iniciar Trabajo de copia de seguridad** para ejecutar el trabajo de copia de seguridad inmediatamente. La ventana de progreso muestra el estado del trabajo de copia de seguridad y, cuando finaliza el trabajo, el estado cambia de "Nunca ejecutado" a "Completado".

Para ver el estado del último trabajo de copia de seguridad que se ha ejecutado, pulse en el separador Trabajos. Se puede acceder a todos los registros de trabajo desde el menú de acciones. Pulse **Acción** y seleccione **Historial/Registros**.
{:tip}

Para obtener más información sobre la restauración de VM o Archivos y carpetas, consulte [Restauración de datos de vSphere](/docs/infrastructure/Backup?topic=Backup-VRARestore#VRARestore).
