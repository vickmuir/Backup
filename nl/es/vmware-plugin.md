---

copyright:
  years: 1994, 2019
lastupdated: "2019-04-01"

keywords: IBM Cloud Backup, VMware, VRA, vSphere Recovery Agent, plug-in, plugin, EVault, Carbonite, vSphere

subcollection: Backup

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Instalación de vSphere Recovery Agent
{: #VRA}

vSphere Recovery Agent (VRA) es una aplicación de Windows, que puede realizar una copia de seguridad y restaurar VMDK de hasta 10 TB. vSphere Recovery Agent se puede instalar en una máquina virtual física que tenga acceso de red local al vCenter que desea proteger. Para un mejor rendimiento, instale VRA en una máquina que esté en la misma subred que el vCenter. Para distribuir la carga de trabajo, hasta cinco VRA pueden proteger las VM conectadas a un vCenter.

En un clúster extendido vSAN, cada VM tiene un sitio preferido. De forma ideal, se instala un VRA local en cada sitio que realice copia de seguridad de las VM preferidas de ese sitio. Si se traslada una VM a otro sitio distinto (por motivos de mantenimiento o por fallos) puede que el rendimiento de copia de seguridad se degrade pero aún sea aceptable.


## Solicitud del plugin
{: #orderingVRAPlugin}

{{site.data.keyword.cloud_notm}} proporciona vSphere Recovery Agent (VRA) de forma gratuita. Si dispone de una suscripción actualizada a {{site.data.keyword.backup_notm}}, puede descargar el plugin del portal de {{site.data.keyword.backup_notm}}.

## Instalación del plugin
{: #installVRAPlugin}

Asegúrese de que la Gestión de alimentación esté inhabilitada en el servidor donde instale VRA.
{: important}

1. Descargue el kit de instalación de `http://downloads.service.softlayer.com/evault/`. A continuación, efectúe una doble pulsación en el kit de instalación.
2. En el mensaje de confirmación, pulse **Sí**.
3. En la página de bienvenida, pulse **Siguiente**.
4. En la página Acuerdo de licencia de usuario final, lea el acuerdo de licencia. Si está de acuerdo con los términos, pulse **Acepto los términos del acuerdo de licencia** y después pulse **Siguiente**.
5. En la página Carpeta de destino, realice una de las siguientes acciones.
   * Para instalar VRA en la ubicación predeterminada, pulse **Siguiente**.
   * Para instalar VRA en otra ubicación, pulse **Cambiar**. En el cuadro de diálogo Cambiar carpeta de destino, vaya a la nueva carpeta de instalación o escríbala en el recuadro Nombre de carpeta. Pulse **Aceptar**. En la página Carpeta de destino, pulse **Siguiente**.
6. En la página para registrar el agente con el portal, especifique la información siguiente.
   * En el campo **Dirección de red**, escriba `ev-webcc01.service.softlayer.com`.
   * En el campo **Puerto**, escriba `8086`.
   * En el campo **Nombre de usuario**, escriba el nombre de usuario de {{site.data.keyword.backup_notm}} que gestionará VRA.
   * En el campo **Contraseña**, escriba la contraseña del usuario de {{site.data.keyword.backup_notm}} especificado.
7.	Pulse **Siguiente**. Cuando termine la instalación, pulse **Finalizar**.

## Configuración de vSphere Recovery Agent
{: #configureVRA}

Una vez que VRA esté instalado, tiene que configurarlo en el portal de {{site.data.keyword.backup_notm}}.

1. Inicie la sesión en el portal de {{site.data.keyword.backup_notm}}. Para obtener más información sobre cómo acceder al portal de {{site.data.keyword.backup_notm}}, consulte la [Guía de aprendizaje Cómo empezar](/docs/infrastructure/Backup?topic=Backup-getting-started#accessingWebCC).
2. En el separador Sistemas, seleccione el servidor del que desea hacer copia de seguridad.
3. Configure la información de caja fuerte.

   La información de caja fuerte se puede configurar de dos modos distintos: **Automáticamente** o **Manualmente**.<br/>Si se va a configurar el agente por primera vez, se puede configurar con la opción de [Configuración automática](#VRAautoconfig).<br/>Si el sistema se había configurado anteriormente con una caja fuerte, la configuración automática no funciona y se tiene que [configurar manualmente](#VRAmanualconfig).
   {: tip}

4. Configure los [Valores de vCenter](#vCenterSettingsconfig)   

### Configuración automática de la caja fuerte
{: #VRAautoconfig}

Para configurar automáticamente los Valores de caja fuerte, pulse **Configurar automáticamente**. Se ejecuta el asistente de configuración y configura los Valores de caja fuerte. Cuando se haya completado, pulse **Ir al agente** para verificar la información del separador **Valores de caja fuerte**.
 

### Configuración manual de la caja fuerte
{: #VRAmanualconfig}

Para configurar manualmente los Valores de caja fuerte, pulse **Configurar manualmente**.   
1. Pulse **Valores de caja fuerte**.
2. Pulse **Añadir caja fuerte**. Aparecerá la ventana Valores de caja fuerte. En las opciones de **Perfil de caja fuerte**, seleccione la caja fuerte adecuada.
   Si el sistema ya se había configurado anteriormente con una caja fuerte de {{site.data.keyword.backup_notm}}, toda la información se completa automáticamente cuando se selecciona la caja fuerte en Perfil de caja fuerte.
   {:note}

3. Verifique toda la información de la página Valores de caja fuerte y pulse **Guardar**.
4. Al guardar los valores de caja fuerte, la información de la misma se visualiza en el separador **Valores de caja fuerte**.


### Configuración de los Valores del agente de vCenter
{: #vCenterSettingsconfig}
Una vez configurada satisfactoriamente la caja fuerte, es necesario configurar los Valores de vCenter para poder crear y ejecutar trabajos de copia de seguridad.

1. Pulse en el separador **Valores de vCenter**
2. Indique la dirección IP, el nombre de dominio y las credenciales del vCenter que desea proteger.
   El usuario debe tener acceso administrativo al vCenter para llevar a cabo esta tarea satisfactoriamente.
   {:note}

3. Inhabilite Change Block Tracking (CBT) eliminando la marca de selección. CBT es una característica de VMware que realiza el seguimiento de los sectores de disco modificados y mejora el rendimiento de las copias de seguridad de VM, y que el Agente de vSphere habilita automáticamente.
4. Pulse **Probar conexión de vCenter**. Los resultados se muestran en una ventana nueva. Si la información de inicio de sesión proporcionada es correcta, aparece el mensaje “Las credenciales de vCenter se han validado satisfactoriamente”.
5. Pulse **Guardar** para guardar los valores.

## Pasos siguientes
{: #VRAnextteps}
1. [Configurar, planificar y ejecutar un trabajo de copia de seguridad](/docs/infrastructure/Backup?topic=Backup-ConfigureVRA)
2. [Restaurar los datos de vSphere](/docs/infrastructure/Backup?topic=Backup-VRARestore#VRARestore)

Conéctese a la red de {{site.data.keyword.BluSoftlayer_full}} con {{site.data.keyword.BluVPN}} para poder acceder y descargar la guía del usuario desde la [Documentación descargable de {{site.data.keyword.backup_notm}}![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](http://downloads.service.softlayer.com/evault/Documentation/){:new_window}.
{:tip}
