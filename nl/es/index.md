---

copyright:
  years: 2014, 2018
lastupdated: "2018-06-05"

---
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}

# Iniciación a los servicios de copia de seguridad de EVault

Las copias de seguridad garantizan que los datos se almacenan de forma segura fuera de su dispositivo y están protegidos si se pierden. La copia de seguridad de EVault es un sistema de copia de seguridad automático basado en agente que se gestiona mediante el programa de utilidad de gestión basado en navegador WebCC de EVault y que proporciona a los usuarios un método de hacer copia de seguridad de los datos entre servidores de uno o varios centros de datos de la red {{site.data.keyword.BluSoftlayer_full}}. Los administradores pueden establecer que las copias de seguridad sigan una planificación horaria, diaria, semanal o personalizada que abarque sistemas completos, directorios específicos o incluso archivos individuales. Los plugins adicionales permiten la compatibilidad con software como Microsoft Exchange y Microsoft SQL, así como con otros tipos de software de otros proveedores, y permiten a los usuarios realizar una restauración de la configuración nativa si es necesario.

## Solicitud de EVault 

Hay dos formas de adquirir el servicio de copia de seguridad de EVault:

- Adquirir EVault al solicitar un servidor
- Adquirir EVault como actualización

### Adquirir EVault al solicitar un servidor

1. Inicie una sesión en el [catálogo de IBM Cloud](https://console.bluemix.net/catalog/){:new_window} o en el [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}
2. Solicite un servidor nativo mensual. [Aquí](https://console.bluemix.net/docs/bare-metal/baremetal-provision.html){:new_window} encontrará más información sobre cómo solicitar servidores nativos.
3. Se le redirigirá al portal de gestión para completar el pedido. <br/>
  **Nota**: el servicio de copia de seguridad de EVault no está disponible cuando se solicita un servidor de facturación por hora. Sin embargo, el servicio se puede añadir posteriormente como una actualización. 
4. En la sección **Complementos**, elija una de las opciones de EVault (que no sea "Ninguno").
6. En la parte inferior de la página, pulse **Añadir a pedido**. Se muestra la página de pago.
7. En la página de **PAGO**, busque la sección Nombres de host y de dominio y especifique los nombres de host y de dominio. Puede elegir el nombre de host y el dominio que desee.
8. En la parte derecha de la página de **PAGO**, pulse los recuadros de selección **Términos del servicio de nube** y **Acuerdo de servicio de terceros**.
9. Confirme o especifique la información sobre el pago y pulse **Enviar pedido**. Se le redirigirá a una pantalla con el número de su pedido de suministro. Puede imprimir la pantalla, ya que también es su recibo del pedido de suministro. <br/>**Nota**: también puede guardar este pedido sin adquirirlo pulsando **Guardar como presupuesto**.

Se enviarán una serie de correos electrónicos al administrador: acuse de recibo del pedido de suministro, aprobación y proceso del pedido de suministro y suministro completado. El correo electrónico de suministro completado incluye un enlace a la página *Detalles del dispositivo* después de que inicie una sesión en {{site.data.keyword.cloud_notm}}. También puede iniciar la sesión directamente en el {{site.data.keyword.slportal}}.

**Confirme la adquisición del servicio EVault**
1. En el [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}, seleccione **Dispositivos** > **Lista de dispositivos** en el menú principal. 
2. Localice el nuevo servidor que ha solicitado.
  - Si hay un icono de reloj junto al url, tendrá que esperar para continuar con la confirmación de compra de EVault. Puede renovar la página para ver el estado actualizado en el nuevo servidor. Cuando deje de aparecer el icono del reloj, puede continuar con los pasos siguientes para confirmar la compra del servicio EVault.
  - Cuando deje de mostrarse el icono de reloj para el servidor, pulse el enlace (el url del servidor) para ir a la página **Detalles del dispositivo**. 
3. Pulse el separador **Almacenamiento** para ver la información de EVault.
4. Examine la sección EVault y verifique que se muestra el tamaño seleccionado durante el proceso de adquisición de EVault junto al enlace EVault.

### Adquirir EVault como actualización

**Seleccione el servidor en el que desea instalar EVault**
1. Inicie una sesión en el [catálogo de IBM Cloud](https://console.bluemix.net/catalog/){:new_window} o en el [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}
2. Seleccione **Dispositivos** > **Lista de dispositivos** en el menú principal. Busque el dispositivo al que desea añadir el servicio EVault.
3. Pulse el nombre del dispositivo para ir a la página de detalles del dispositivo.

**Añada (adquiera) el servicio EVault**
1. Pulse el separador **Almacenamiento** y localice la sección EVault casi al final de la página.
2. Pulse el enlace **Añadir**.
3. En la ventana emergente, seleccione una ubicación o acepte el valor predeterminado y seleccione un tamaño.
4. Pulse **Continuar**
5. Pulse el recuadro de selección si está de acuerdo con los términos y condiciones.
6. Pulse **Realizar pedido**.

**Confirme la adquisición del servicio EVault**
1. Renueve la página **Detalles del dispositivo** y asegúrese de que el separador **Almacenamiento** está seleccionado.
2. Examine la sección EVault y verifique que se muestra el tamaño seleccionado durante el proceso de adquisición de EVault junto al enlace EVault. <br /> **Nota**: si el tamaño de almacenamiento de EVault sigue mostrando la capacidad cero, es posible que tenga que volver a renovar la página. 

## Acceso y visualización de los detalles de almacenamiento de copia de seguridad de EVault en el {{site.data.keyword.slportal}}

Los detalles de almacenamiento del servicio de copia de seguridad de EVault se pueden ver mediante el {{site.data.keyword.slportal}} en cualquier momento. Los detalles que se pueden ver incluyen contraseña, dirección de almacenamiento y uso asociado con el servicio de copia de seguridad de EVault seleccionado. 

1. Para acceder a la pantalla **Almacenamiento de copia de seguridad de EVault** en el [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}, inicie una sesión con sus credenciales exclusivas.
2. Pulse **Almacenamiento** y seleccione **Copia de seguridad** en la lista desplegable.
2. Pulse en cualquier lugar de la fila correspondiente a la copia de seguridad de EVault que desee para ver sus detalles de almacenamiento. En esta vista la contraseña no resulta visible. Continúe con el paso siguiente para ver la contraseña asociada con el servicio de copia de seguridad de EVault.
3. Pulse el recuadro de selección **Mostrar** junto al campo **Contraseña** para ver la contraseña correspondiente al servicio de copia de seguridad de EVault seleccionado.

Para muchos productos y servicios de {{site.data.keyword.BluSoftlayer_full}}, la característica de almacenamiento de contraseñas dentro del {{site.data.keyword.slportal}} solo se utiliza para almacenar o realizar el seguimiento de la contraseña, y los cambios realizados en la contraseña dentro del {{site.data.keyword.slportal}} no se aplican al producto o servicio. Este _no_ es el caso del servicio de copia de seguridad de EVault. Los cambios realizados en la contraseña de la copia de seguridad de EVault en el {{site.data.keyword.slportal}} se realizarán en el propio servicio. Cuando realice cambios, tenga en cuenta que afectarán directamente al servicio. Para restablecer la contraseña, siga los pasos del apartado sobre [Cómo cambiar una contraseña de copia de seguridad de EVault en el {{site.data.keyword.slportal}}](/docs/infrastructure/Backup/change-password-evault-backup-service.html).

## Instalación del agente de EVault

El agente de EVault recibe soporte en los siguientes sistemas operativos:

### Windows
 - Windows Server 2012 R2
 - Windows Server 2012
 - Windows Server 2008 R2
 - Windows Server 2008

### Linux
 - CentOS 7.x
 - CentOS 6.x
 - Debian GNU/Linux 9.x
 - Debian GNU/Linux 8.x
 - Debian GNU/Linux 7.x
 - Red Hat Enterprise Linux 7.x
 - Red Hat Enterprise Linux 6.x
 - Ubuntu Linux 16.04
 - Ubuntu Linux 14.04

Siga las instrucciones adecuadas para su sistema operativo:
- [Instalación del cliente de copia de seguridad de EVault en Linux](install-evault-backup-client-linux.html)
- [Instalación del cliente de copia de seguridad de EVault en Windows](install-evault-backup-client-windows.html)
- [Instalación del cliente de copia de seguridad de EVault en Windows 2016](install-evault-windows2016.html)

## Acceso a WebCentralControl (WebCC) para copia de seguridad de EVault

WebCentralControl (WebCC) es el cliente que se utiliza cuando se interactúa con el servicio de copia de seguridad de EVault que ofrece {{site.data.keyword.BluSoftlayer_full}}. WebCC es un cliente basado en navegador que se ejecuta en nuestra red privada y que permite el control completo de cualquier servicio de copia de seguridad de EVault, incluidas operaciones de configuración y de restauración. Siga estos pasos para acceder a WebCC de copia de seguridad de EVault.

1. Acceda a la red privada a través de VPN. <br/>
    **Nota**: no se puede acceder a WebCC a través de la red pública. Se debe establecer una conexión VPN para poder acceder a WebCC.
2. Acceda a la pantalla Almacenamiento de copia de seguridad de EVault en el [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}.
3. Pulse en cualquier lugar de la fila correspondiente a la copia de seguridad de EVault que desee para ampliar la vista.
3. Pulse **Inicio de sesión de WebCC** para iniciar el cliente WebCC en el navegador.

## Configuración del agente de EVault en WebCC

Después de haber solicitado el servicio EVault y de haber instalado el agente en el servidor, puede empezar a crear copias de seguridad de los datos. Siga estos pasos para configurar el agente, planificar la retención y empezar su primer trabajo de copia de seguridad.

1. Inicie una sesión en WebCc.
2. Pulse **Todos los agentes**> **Agentes no configurados**.
3. Pulse el enlace **Este es un nuevo agente que me gustaría configurar**. Siga los pasos del proceso y especifique lo siguiente:
   1. Configuración del agente: especifique la descripción del agente y pulse **Siguiente**.
   2. Selección de tipo de trabajo: especifique el nombre del trabajo, la descripción del trabajo y el tipo de origen de la copia de seguridad y pulse **Siguiente**.
   3. Selección: seleccione los directorios y pulse **Incluir...**
   4. Opciones: especifique contraseñas
   5. Planificación: pulse **Añadir** para crear una planificación y pulse **Siguiente**.
   6. Seleccione el almacén predeterminado y pulse **Aceptar**.
   7. Pulse **Guardar**.
4. Cree una planificación de retención:
   1. Seleccione **Editar** > **Configuración del agente**.
   2. Pulse **Añadir**.
   3. Especifique los detalles de retención.
   4. Pulse **Aceptar**.
   5. Pulse **Guardar**.
   **Nota**: [aquí](evault-backup-faq.html#how-do-the-retention-schemes-work-) encontrará más información sobre cómo funcionan los esquemas de retención
5. Ejecute el agente e inicie una copia de seguridad.
   1. Pulse **Todos los agentes** y seleccione el agente que acaba de configurar.
   2. Pulse **Ejecutar copia de seguridad**.
   3. Confirme el destino y seleccione un esquema de retención.
   4. Pulse **Iniciar copia de seguridad**. Puede ver los detalles de la copia de seguridad mientras se está ejecutando el proceso.
   5. Cuando finalice la copia de seguridad, pulse **Cerrar**.
   
**Nota**: [aquí](configure-simple-file-backup-linux.html) encontrará más información sobre cómo puede configurar copias de seguridad simples a nivel de archivo en Linux.

## Qué sucede a continuación

Los sistemas WebCC están plenamente documentados y se puede acceder a soporte para la aplicación dentro de WebCC. Pulse **Ayuda**, indicada mediante un signo de interrogación en un círculo azul, en la esquina superior derecha. Pulse cualquier artículo o tema en la barra de navegación de la parte izquierda del recuadro emergente para ver más información.


