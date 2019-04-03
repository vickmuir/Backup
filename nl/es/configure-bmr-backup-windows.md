---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-05"

keywords:

subcollection: Backup

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Configuración de un trabajo de copia de seguridad de BMR en Windows
{: #configureBMR}

Tiene que adquirir el plug-in de BMR para crear una copia de seguridad BMR. BMR solo está disponible para servidores nativos Windows. La opción BMR no está disponible para VSI. Para obtener más información, consulte [Instalación del plugin de restauración desde cero](/docs/infrastructure/Backup?topic=Backup-BMRplugin#BMRplugin)
{:important}

## Inicio del portal de {{site.data.keyword.backup_notm}}
{: #startWebCCBMR}

Debe estar conectado a la red privada de {{site.data.keyword.BluSoftlayer_full}} para poder iniciar el portal de {{site.data.keyword.backup_notm}}.
{:important}

1. Inicie la sesión en la [consola de {{site.data.keyword.cloud_notm}}](https://{DomainName}/){:new_window} y pulse el icono de **menú** de la parte superior izquierda. Seleccione **Infraestructura clásica**.<br/>
   También puede iniciar la sesión en el [{{site.data.keyword.slportal}} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://control.softlayer.com/){:new_window}.
2. Pulse en **Almacenamiento** > **Copia de seguridad** para visualizar los servidores con servicios de copia de seguridad.
3. Seleccione el servidor donde se encuentran los archivos de los que va a hacer copia de seguridad. Pulse la flecha de expansión hacia la derecha para revelar el enlace del portal de {{site.data.keyword.backup_notm}}.
4. Pulse el **inicio de sesión en el portal de {{site.data.keyword.backup_notm}}** para iniciar el cliente del portal en su navegador.

   Si el portal de {{site.data.keyword.backup_notm}} no se inicia, es posible que tenga un problema con la conexión VPN. También puede ver un mensaje que indique que el método de envío no es seguro. Esto es normal; continúe con el envío del formulario.
   {:tip}

## Configuración de un trabajo de copia de seguridad de BMR

1. En el panel de navegación izquierdo, pulse **Todos los agentes** para visualizar los agentes actuales de {{site.data.keyword.backup_notm}}.
2. Pulse **Este es un nuevo agente que me gustaría configurar**.
3. Escriba un nombre de trabajo y una descripción de trabajo para el trabajo que va a crear.
4. Para **Tipo de origen de copia de seguridad**, seleccione el tipo de sistema de archivos en la lista y luego pulse **Siguiente**
5. Aparecerá el menú **Selección de tipo de trabajo**. Marque el recuadro que hay junto a **Restauración desde cero** y pulse **Siguiente** para continuar.
6. Pulse **Sí** en la ventana de confirmación.
7. La pantalla muestra que el nuevo trabajo ahora está en el conjunto de copia de seguridad. Pulse **Siguiente**.
8. La pantalla muestra opciones de cifrado y opciones avanzadas de seguridad. Estas opciones normalmente no se necesitan. Pulse **Siguiente**.   
9. En la página **Crear una planificación**, tiene dos opciones.
   - Pulse **Siguiente** para crear un trabajo manual y continuar para ejecutar el nuevo trabajo.
   - Pulse **Añadir** para planificar un trabajo de copia de seguridad basado en tiempo.
     1. Seleccione los días y la hora del día en que desea ejecutar las copias de seguridad.
     2. Seleccione el esquema de retención.

        Para obtener más información sobre los esquemas de retención, consulte las [Preguntas frecuentes](/docs/infrastructure/Backup?topic=Backup-faqs).
        {:tip}
     3. Después de haber configurado la planificación de copia de seguridad, pulse **Aceptar** para guardarla. El trabajo planificado se añade a la lista de trabajos planificados.
10. Seleccione una caja fuerte para el trabajo de seguridad y pulse **Guardar cambios**.


## Ejecución de un trabajo de copia de seguridad de BMR

  - Si ha planificado un trabajo de copia de seguridad basado en tiempo, no es necesario que haga nada más. El trabajo se ejecuta automáticamente según lo planificado.
  - Si ha configurado un trabajo manual (sin una planificación basada en tiempo), puede ejecutarlo seleccionando su fila en la lista de trabajos y pulsando **Ejecutar copia de seguridad**. <br/> Al igual que sucede con los trabajos basados en tiempo, puede elegir el **Esquema de retención** y las **Opciones avanzadas de copia de seguridad**. Después de completar las opciones de configuración, pulse **Iniciar copia de seguridad** para iniciar el trabajo.
