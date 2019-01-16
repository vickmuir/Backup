---

copyright:
  years: 2014, 2018
lastupdated: "2018-12-14"

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Iniciación a los servicios de {{site.data.keyword.backup_notm}}

Las copias de seguridad garantizan que los datos se almacenan de forma segura fuera de su dispositivo y están protegidos si se pierden. {{site.data.keyword.backup_full}} es un sistema de copia de seguridad automático basado en agente que se gestiona mediante el programa de utilidad de gestión basado en navegador del portal de {{site.data.keyword.backup_notm}}. {{site.data.keyword.backup_notm}} proporciona a los usuarios un método de hacer copia de seguridad de los datos entre servidores de uno o varios centros de datos de la red de {{site.data.keyword.BluSoftlayer_full}}. Los administradores pueden establecer que las copias de seguridad sigan una planificación diaria, semanal o personalizada que abarque sistemas completos, directorios específicos o incluso archivos individuales. Los plugins adicionales garantizan la compatibilidad con software como Microsoft Exchange y Microsoft SQL y otros tipos de software de terceros y permiten a los usuarios completar una restauración desde cero.

## Pedido de {{site.data.keyword.backup_notm}}

Puede adquirir el servicio {{site.data.keyword.backup_notm}} de dos maneras.

- [Adquisición de copias de seguridad cuando se solicita un servidor](#purchasing-ibm-cloud-backup-when-you-order-a-server).
- [Adquisición de copias de seguridad como actualización](#purchasing-ibm-cloud-backup-as-an-upgrade).

Para obtener más información sobre los precios, consulte [Almacenamiento de {{site.data.keyword.backup_notm}} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.ibm.com/cloud/backup-and-restore){:new_window} y [{{site.data.keyword.backup_notm}} en IBM Cloud ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://www.ibm.com/cloud/evault/pricing){:new_window}.

### Adquisición de {{site.data.keyword.backup_notm}} cuando se solicita un servidor

1. Inicie sesión en el [Catálogo de IBM Cloud ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://{DomainName}/catalog/){:new_window} o el [{{site.data.keyword.slportal}} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://control.softlayer.com/){:new_window}
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

#### Confirmación de la compra de {{site.data.keyword.backup_notm}}
1. En la [consola de {{site.data.keyword.cloud_notm}} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://{DomainName}/){:new_window}, pulse el icono de **menú** de la parte superior izquierda. Seleccione **Infraestructura clásica**.</br>
   También puede iniciar la sesión en [{{site.data.keyword.slportal}} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://control.softlayer.com/){:new_window}.
2. Pulse **Dispositivo** > **Lista de dispositivos**.
2. Localice el nuevo servidor que ha solicitado.
  - Si ve un icono de reloj junto al url, tiene que esperar para continuar con la confirmación de compra de {{site.data.keyword.backup_notm}}. Puede renovar la página para ver el estado actualizado en el nuevo servidor. Cuando deje de aparecer el icono del reloj, puede continuar con los pasos siguientes para confirmar la compra del servicio de {{site.data.keyword.backup_notm}}.
  - Cuando deje de mostrarse el icono de reloj para el servidor, pulse el enlace (el url del servidor) para ir a la página **Detalles del dispositivo**.
3. Pulse el separador **Almacenamiento** para ver la información de {{site.data.keyword.backup_notm}}.
4. Examine la sección {{site.data.keyword.backup_notm}} y verifique que se muestra el tamaño seleccionado durante el proceso de adquisición.

### Adquisición de {{site.data.keyword.backup_notm}} como actualización

#### Seleccione el servidor en el que desea instalar {{site.data.keyword.backup_notm}}

1. Inicie una sesión en la [consola de {{site.data.keyword.cloud_notm}} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://{DomainName}){:new_window} y pulse el icono de **menú** de la parte superior izquierda. Seleccione **Infraestructura clásica**.</br>
   También puede iniciar la sesión en [{{site.data.keyword.slportal}} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://control.softlayer.com/){:new_window}.
2. Seleccione **Dispositivos** > **Lista de dispositivos** en el menú principal. Busque el dispositivo al que desea añadir el servicio de copia de seguridad.
3. Pulse el nombre del dispositivo para ir a la página **Detalles del dispositivo**.

#### Adición (adquisición) del servicio {{site.data.keyword.backup_notm}}
1. Pulse el separador **Almacenamiento** y desplácese hacia abajo para localizar la sección {{site.data.keyword.backup_notm}}.
2. Pulse el enlace **Añadir**.
3. En la ventana, seleccione una ubicación y un tamaño.
4. Seleccione el tipo de pago y pulse **Continuar**
5. Escriba el **Código de promoción** si tiene uno y pulse **Recalcular**.
6. Revise el pedido y pulse el enlace para leer los términos y condiciones.
7. Pulse el recuadro de selección si está de acuerdo con los términos y condiciones.
7. Pulse **Realizar pedido**.

#### Confirmación de la compra de la actualización de {{site.data.keyword.backup_notm}}
1. Renueve la página **Detalles del dispositivo** y asegúrese de que el separador **Almacenamiento** está seleccionado.
2. Examine la sección {{site.data.keyword.backup_notm}} y verifique que se muestra el tamaño seleccionado durante el proceso de adquisición.

   Si el tamaño de almacenamiento de copia de seguridad sigue mostrando la capacidad cero, es posible que tenga que volver a renovar la página.
   {:tip}

## Acceso y visualización de los detalles de almacenamiento de {{site.data.keyword.backup_notm}}

Puede ver los detalles de almacenamiento del servicio en la [consola de {{site.data.keyword.cloud_notm}}](https://{DomainName}/){:new_window} y en el {{site.data.keyword.slportal}} siempre que lo desee. Los detalles que se pueden ver incluyen contraseña, dirección de almacenamiento y uso asociado con el servicio de {{site.data.keyword.backup_notm}} seleccionado.

1. Inicie una sesión en la [consola de {{site.data.keyword.cloud_notm}}](https://{DomainName}){:new_window} y pulse el icono de **menú** de la parte superior izquierda. Seleccione **Infraestructura clásica**.</br>
   También puede iniciar la sesión en [{{site.data.keyword.slportal}} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://control.softlayer.com/){:new_window}.
2. Pulse **Almacenamiento** y seleccione **Copia de seguridad** en la lista.
2. Pulse en cualquier lugar de la fila correspondiente a la caja fuerte cuyos detalles de almacenamiento desea ver. En esta vista la contraseña no resulta visible.
3. Pulse el recuadro de selección **Mostrar** junto al campo **Contraseña** para ver la contraseña correspondiente al servicio de {{site.data.keyword.backup_notm}} seleccionado.

Los cambios realizados en la contraseña de la copia de seguridad de {{site.data.keyword.backup_notm}} en el {{site.data.keyword.slportal}} se realizan en el propio servicio. Para restablecer la contraseña, siga los pasos de la sección [Cambio de la contraseña del servicio de copia de seguridad](change-password.html).
{:important}

## Instalación del agente de {{site.data.keyword.backup_notm}}

El agente de {{site.data.keyword.backup_notm}} está soportado en los sistemas operativos siguientes:

**Windows**
 - Windows Server 2016
 - Windows Server 2012 R2
 - Windows Server 2012
 - Windows Server 2008 R2
 - Windows Server 2008

**Linux**
 - CentOS 7.x
 - CentOS 6.x
 - Debian GNU/Linux 9.x
 - Debian GNU/Linux 8.x
 - Debian GNU/Linux 7.x
 - RHEL 7.x
 - RHEL 6.x
 - Ubuntu Linux 16.04
 - Ubuntu Linux 14.04

Siga las instrucciones adecuadas para su sistema operativo,
- [Instalación del cliente de copia de seguridad en Linux](install-backup-client-linux.html)
- [Instalación del cliente de copia de seguridad en Windows](install-backup-client-windows.html)
- [Instalación del cliente de copia de seguridad en Windows 2016](install-backup-client-windows2016.html)

## Acceso al portal de {{site.data.keyword.backup_notm}} (anteriormente conocido como WebCC)

El portal de {{site.data.keyword.backup_notm}} se utiliza para interactuar con todos los servicios de {{site.data.keyword.backup_notm}} que ofrece {{site.data.keyword.BluSoftlayer_full}}. El portal de {{site.data.keyword.backup_notm}} es un cliente basado en navegador que se ejecuta en la red privada de {{site.data.keyword.BluSoftlayer_full}} y que permite el control completo de cualquier servicio de {{site.data.keyword.backup_notm}}, incluidas operaciones de configuración y de restauración.

1. Acceda a la red privada a través de VPN.

   No se puede acceder al portal de {{site.data.keyword.backup_notm}} a través de la red pública. En primer lugar se debe establecer una conexión VPN.
   {:important}
2. Acceda a la pantalla de almacenamiento de copia de seguridad en [{{site.data.keyword.slportal}} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://control.softlayer.com/){:new_window}.
3. Pulse en cualquier lugar de la fila del servicio de {{site.data.keyword.backup_notm}} que desea ver para expandir la vista.
4. Pulse el **inicio de sesión en el portal de {{site.data.keyword.backup_notm}}** para iniciar el cliente del portal en su navegador.

## Configuración del agente de copia de seguridad y de la planificación de copias de seguridad

Después de haber solicitado el {{site.data.keyword.backup_notm}} y de haber instalado el agente en el servidor, puede empezar a crear copias de seguridad de los datos. Siga estos pasos para configurar el agente, planificar la retención y empezar su primer trabajo de copia de seguridad.

1. Inicie una sesión en el portal de {{site.data.keyword.backup_notm}}.
2. Pulse **Todos los agentes**> **Agentes no configurados**.
3. Pulse el enlace **Este es un nuevo agente que me gustaría configurar**. Siga los pasos del proceso y especifique la siguiente información:
   1. Configuración del agente: especifique la descripción del agente y pulse **Siguiente**.
   2. Selección de tipo de trabajo: especifique el nombre del trabajo, la descripción del trabajo y el tipo de origen de la copia de seguridad y pulse **Siguiente**.
   3. Selección: seleccione los directorios y pulse **Incluir...**
   4. Opciones: especifique contraseñas
   5. Planificación: pulse **Añadir** para crear una planificación y pulse **Siguiente**.
   6. Seleccione la caja fuerte predeterminada y pulse **Aceptar**.
   7. Pulse **Guardar**.
4. Cree una planificación de retención.
   1. Seleccione **Editar** > **Configuración del agente**.
   2. Pulse **Añadir**.
   3. Especifique los detalles de retención.
   4. Pulse **Aceptar**.
   5. Pulse **Guardar**.

      Para obtener más información sobre los esquemas de retención, consulte las [Preguntas frecuentes](faqs.html).
      {:tip}
5. Ejecute el agente e inicie una copia de seguridad.
   1. Pulse **Todos los agentes** y seleccione el agente que ha configurado.
   2. Pulse **Ejecutar copia de seguridad**.
   3. Confirme el destino y seleccione un esquema de retención.
   4. Pulse **Iniciar copia de seguridad**. Puede ver los detalles de la copia de seguridad mientras se está ejecutando el proceso.
   5. Cuando finalice la copia de seguridad, pulse **Cerrar**.

Para obtener más información, consulte la sección [Configuración de una copia de seguridad simple a nivel de archivo en Linux](configure-simple-file-backup-linux.html).
{:tip}

## Obtención de ayuda en línea

Los sistemas del portal de {{site.data.keyword.backup_notm}} están plenamente documentados y se puede acceder a soporte para la aplicación dentro del propio portal de {{site.data.keyword.backup_notm}}. Pulse el signo de interrogación blanco dentro de un círculo azul que se encuentra en la parte superior derecha para obtener **Ayuda**. Pulse cualquier artículo o tema en la barra de navegación de la parte izquierda para ver más información.
