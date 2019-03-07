---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-28"

keywords: EVault, Carbonite, IBM Cloud Backup, Enterprise Backup

subcollection: Backup

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Suministro de {{site.data.keyword.backup_notm}}
{: #ordering}

Puede adquirir el servicio {{site.data.keyword.backup_notm}} de dos maneras.

- [Adquisición de copias de seguridad cuando se solicita un servidor](#purchasingwithserver).
- [Adquisición de copias de seguridad como actualización](#purchasingasupgrade).

Para obtener más información sobre los precios, consulte [Almacenamiento de {{site.data.keyword.backup_notm}} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.ibm.com/cloud/backup-and-restore){:new_window} y [{{site.data.keyword.backup_notm}} en IBM Cloud ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.ibm.com/cloud/evault/pricing){:new_window}.

## Adquisición de {{site.data.keyword.backup_notm}} cuando se solicita un servidor
{: #purchasingwithserver}

1. Inicie la sesión en el [catálogo de IBM Cloud ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://{DomainName}/catalog/){:new_window} o el [{{site.data.keyword.slportal}} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://control.softlayer.com/){:new_window}
2. Solicite un servidor nativo mensual. Para obtener más información sobre el pedido de servidores nativos, consulte [Creación de un servidor nativo personalizado](https://{DomainName}/docs/bare-metal/baremetal-provision.html){:new_window}.
   1. Seleccione la cantidad y la opción de facturación. Especifique los nombres de host y de dominio. Puede elegir el nombre de host y de dominio que desee.

      El servicio {{site.data.keyword.backup_notm}} no está disponible cuando se solicita un servidor de facturación por horas. Sin embargo, el servicio se puede añadir posteriormente como una actualización.
      {:tip}
   2. Seleccione la ubicación.
   3. Seleccione Configuración de servidor y tipo de imagen de SO. También puede elegir varios complementos.
   4. En la sección **Discos de almacenamiento**, pulse **Complementos** y seleccione **{{site.data.keyword.backup_notm}}**. Elija la opción que coincida con lo que necesita.
   5. En **Interfaz de red**, seleccione la Velocidad de puerto de enlace ascendente y los complementos que desee.
3. A la derecha, revise el resumen de su pedido.
4. Después de revisar los términos y condiciones, marque el recuadro de selección **He leído y acepto los acuerdos de servicio de terceros**.
5. Pulse **Suministrar**. Se le redirigirá a una pantalla con el número de su pedido de suministro. Puede imprimir la pantalla, ya que también es su recibo del pedido de suministro.

   También puede guardar este pedido sin adquirirlo pulsando **Guardar como presupuesto**.
   {:tip}

Se enviarán una serie de correos electrónicos al administrador: acuse de recibo del pedido de suministro, aprobación y proceso del pedido de suministro y suministro completado. El correo electrónico de suministro completado incluye un enlace a la página *Detalles del dispositivo*, a la que puede acceder después de iniciar una sesión en {{site.data.keyword.cloud_notm}}. También puede iniciar la sesión directamente en el {{site.data.keyword.slportal}}.

### Confirmación de la compra de {{site.data.keyword.backup_notm}}
1. En la [consola de {{site.data.keyword.cloud_notm}} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://{DomainName}/){:new_window}, pulse el icono de **menú** de la parte superior izquierda. Seleccione **Infraestructura clásica**.</br>
   También puede iniciar la sesión en el [{{site.data.keyword.slportal}} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://control.softlayer.com/){:new_window}.
2. Pulse **Dispositivo** > **Lista de dispositivos**.
2. Localice el nuevo servidor que ha solicitado.
  - Si ve un icono de reloj junto al url, tiene que esperar para continuar con la confirmación de compra de {{site.data.keyword.backup_notm}}. Puede renovar la página para ver el estado actualizado en el nuevo servidor. Cuando deje de aparecer el icono del reloj, puede continuar con los pasos siguientes para confirmar la compra del servicio de {{site.data.keyword.backup_notm}}.
  - Cuando deje de mostrarse el icono de reloj para el servidor, pulse el enlace (el url del servidor) para ir a la página **Detalles del dispositivo**.
3. Pulse el separador **Almacenamiento** para ver la información de {{site.data.keyword.backup_notm}}.
4. Examine la sección {{site.data.keyword.backup_notm}} y verifique que se muestra el tamaño seleccionado durante el proceso de adquisición.

## Adquisición de {{site.data.keyword.backup_notm}} como actualización
{: #purchasingasupgrade}

### Seleccione el servidor en el que desea instalar {{site.data.keyword.backup_notm}}

1. Inicie la sesión en la [consola de {{site.data.keyword.cloud_notm}} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://{DomainName}){:new_window} y pulse el icono de **menú** de la parte superior izquierda. Seleccione **Infraestructura clásica**.</br>
   También puede iniciar la sesión en el [{{site.data.keyword.slportal}} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://control.softlayer.com/){:new_window}.
2. Seleccione **Dispositivos** > **Lista de dispositivos** en el menú principal. Busque el dispositivo al que desea añadir el servicio de copia de seguridad.
3. Pulse el nombre del dispositivo para ir a la página **Detalles del dispositivo**.

### Adición (adquisición) del servicio {{site.data.keyword.backup_notm}}
1. Pulse el separador **Almacenamiento** y desplácese hacia abajo para localizar la sección {{site.data.keyword.backup_notm}}.
2. Pulse el enlace **Añadir**.
3. En la ventana, seleccione una ubicación y un tamaño.
4. Seleccione el tipo de pago y pulse **Continuar**
5. Escriba el **Código de promoción** si tiene uno y pulse **Recalcular**.
6. Revise el pedido y pulse el enlace para leer los términos y condiciones.
7. Pulse el recuadro de selección si está de acuerdo con los términos y condiciones.
7. Pulse **Realizar pedido**.

### Confirmación de la compra de la actualización de {{site.data.keyword.backup_notm}}
1. Renueve la página **Detalles del dispositivo** y asegúrese de que el separador **Almacenamiento** está seleccionado.
2. Examine la sección {{site.data.keyword.backup_notm}} y verifique que se muestra el tamaño seleccionado durante el proceso de adquisición.

   Si el tamaño de almacenamiento de copia de seguridad sigue mostrando la capacidad cero, es posible que tenga que volver a renovar la página.
   {:tip}
