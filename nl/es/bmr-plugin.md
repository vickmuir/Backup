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

# Instalación del plugin de restauración nativa

BMR es una solución de recuperación tras desastre para Microsoft Windows. Puede utilizar BMR para restaurar el servidor desde cero después de que se produzca un desastre, como un error del sistema operativo o del hardware. Con BMR puede restaurar rápidamente la imagen del sistema desde una ubicación segura, gestionada por {{site.data.keyword.BluSoftlayer_full}}.

BMR es un producto de Microsoft Windows solo para servidores físicos. No está disponible para servidores virtuales. No se da soporte a las distribuciones de restauraciones desde cero de Linux. BMR sólo está soportado por el agente de copia de seguridad 8.30 o versiones anteriores. (30 de junio de 2018).
{:important}

**Funciones que se proporcionan**

- Restaurar el sistema a un punto en el tiempo seleccionado.
- Restaurar el sistema a partir de copias de seguridad basadas en imagen o en archivo.
- Restaure el sistema a partir de copias de seguridad almacenadas IBM Cloud Backup.
- Una transacción de recuperación que se puede iniciar y que pueda utilizar para restaurar los datos sin un sistema de arranque.
.
## Solicitud del plugin

1. Inicie una sesión en la [consola de {{site.data.keyword.cloud_notm}}](https://{DomainName}/catalog/){:new_window} y pulse el icono **Menú** de la parte superior izquierda. Seleccione **Infraestructura clásica**.

   También puede iniciar la sesión en el [{{site.data.keyword.slportal}} ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://control.softlayer.com/){:new_window}.
2. Haga clic en **Almacenamiento** > **Copia de seguridad** para visualizar los servidores con servicio de copia de seguridad.
3. Seleccione la cuenta y pulse **Solicitar plugins**.
4. Seleccione **Plugin de {{site.data.keyword.backup_notm}} - BMR (restauración desde cero)** y pulse **Continuar**.
5. Escriba su código de promoción, si lo tiene, y pulse **Recalcular**.
6. Se muestran los cargos actualizados. Revise el pedido.
7. Marque el recuadro para indicar que ha leído y que acepta los acuerdos de servicio de terceros.
8. Pulse **Realizar pedido**.

## Descarga de la guía del usuario

Conéctese a la red de {{site.data.keyword.BluSoftlayer_full}} con {{site.data.keyword.BluVPN}} para poder acceder y descargar la guía del usuario desde [Documentación descargable de {{site.data.keyword.backup_notm}} ![External link icon](../../icons/launch-glyph.svg "External link icon")](http://downloads.service.softlayer.com/evault/Documentation/){:new_window}.

## Preguntas más frecuentes

**¿Puedo pasar de un solo disco a una matriz de discos?**

Sí, eso funciona. Sin embargo, debe seleccionar un dispositivo de mayor capacidad debido al decremento del tamaño que causa la matriz RAID.

**¿Qué sucede cuando la imagen se restaura en un disco mayor que el volumen original?**

Si restaura la imagen a un disco mayor que el volumen original, el espacio sobrante se desasigna. Por ejemplo, si tiene una unidad de 500 GB y restaura sus datos en un disco de 1 TB, habrá 500 GB de espacio de disco desasignado. Con Windows 2008, puede utilizar el programa de utilidad de disco integrado para aumentar la partición primaria. Sin embargo, no hay ninguna función incorporada similar en Windows 2003, por lo que debe asignar el espacio de otra forma.

**¿Se puede utilizar BMR para una copia de seguridad normal?**

La copia de seguridad BMR no es una imagen de disco, sino un sistema de copia de seguridad de la imagen del volumen de disco. El sistema no está pensado para que se utilice para copias de seguridad normales, sino para que se utilice en combinación con estas.  

**¿Se puede utilizar BMR para copias de seguridad de base de datos?**

Las copias de seguridad de bases de datos se deben realizar por separado, con los métodos normales de copia de seguridad de IBM. BMR no sustituye la necesidad de disponer de plugins de SQL o de Oracle. Aunque BMR utiliza la tecnología VSS para hacer copia de seguridad de archivos abiertos, no siempre se puede garantizar que los archivos copiados sean coherentes entre transacciones. La recomendación para estos tipos de aplicaciones especializadas es que se creen dos trabajos de copia de seguridad: uno para hacer copia de seguridad del sistema operativo y de los archivos binarios de aplicación y otro para los datos de aplicación. Encontrará una nota sobre este tema al final de la guía del usuario de BMR.

**¿Qué tipos de trabajos de restauración se pueden ejecutar con BMR?**

Puede realizar una restauración completa del sistema o puede seleccionar archivos individuales de la copia de seguridad para restaurarlos. El trabajo de copia de seguridad de BMR puede sustituir el trabajo actual de copia de seguridad de archivos. El proceso de restauración se realiza dentro del sistema operativo, como si fuera un trabajo de copia de seguridad tradicional.

**¿Ofrece BMR funciones de copia de seguridad de archivos abiertos?**

BMR tiene capacidad de copia de seguridad de archivos abiertos. Sin embargo, BMR no sustituye la necesidad de disponer de plugins de SQL o de Oracle. Para obtener más información sobre el plug-in MSSQL, consulte [aquí](mssql-plugin.html).

**¿Cuánto espacio de disco y tiempo requiere una restauración de BMR?**

Una copia de seguridad que se realiza a partir de una instalación predeterminada utiliza unos 6 GB. Este tipo de restauración tarda unos 15 minutos en un puerto de 1 GB. Este proceso también se ve afectado por la velocidad del puerto privado. Si necesita copias de seguridad y restauraciones más rápidas, es posible que se necesite un aumento de velocidad de puerto.
