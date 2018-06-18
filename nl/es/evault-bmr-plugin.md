---

copyright:
  years: 1994, 2018
lastupdated: "2018-06-06"

---
{:new_window: target="_blank"}

# Instalación del plugin EVault Bare Metal Restore

EVault BMR es una solución de recuperación tras desastre para Microsoft Windows que le permite restaurar por completo el servidor a partir de su estado nativo cuando se produce un desastre como un error del sistema operativo o de hardware. Este sistema le permite restaurar rápidamente la imagen del sistema desde una ubicación segura, gestionada por {{site.data.keyword.BluSoftlayer_full}}.

**Nota**: BMR es un producto de Microsoft Windows solo para servidores físicos. No está disponible para servidores virtuales. No se da soporte a las distribuciones Bare Metal Restores para Linux. BMR solo recibe soporte en EVault Agent 8.30 o inferior. (30 de junio de 2018).

## Funciones que se proporcionan

- Restaurar el sistema a un punto en el tiempo seleccionado.
- Restaurar el sistema a partir de copias de seguridad basadas en imagen o en archivo.
- Restaurar el sistema a partir de copias de seguridad guardadas en EVault.
- Una transacción de recuperación que se puede iniciar y que le permitirá restaurar los datos sin un sistema de arranque.

## Solicitar el plugin

1. Inicie una sesión en [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}.
2. Pulse **Almacenamiento** > **Copia de seguridad**.
3. Seleccione la cuenta de EVault y pulse **Solicitar plugins**.
4. Seleccione **Plugin de EVault - BMR (Bare Metal Restore)** y pulse **Continuar**.
5. Escriba su código de promoción si lo tiene y pulse **Recalcular**.
6. Se muestran los cargos actualizados. Revise el pedido.
7. Marque los recuadros para indicar que ha leído el Acuerdo de servicio maestro y que acepta los Términos de software de terceros. 
8. Pulse **Realizar pedido**.

## Guía del usuario

Conecte con la red de {{site.data.keyword.BluSoftlayer_full}} con {{site.data.keyword.BluVPN}} para poder descargar el archivo EVault System Restore v8.3 - User Guide.pdf desde la [Documentación descargable de EVault](http://downloads.service.softlayer.com/evault/Documentation/){:new_window}.

## Preguntas más frecuentes

### ¿Puedo migrar de un solo disco a una matriz RAID?

Sí, esto funcionará. Sin embargo, debe seleccionar un dispositivo de mayor capacidad por el decremento del tamaño que provocará la matriz RAID.

### ¿Qué ocurre si restauro la imagen a un disco mayor que el volumen original?

Si restaura la imagen a un disco mayor que el volumen original, el espacio sobrante se desasigna. Por ejemplo, si tiene una unidad de 500 GB y restaura sus datos a un disco de 1 TB, habrá 500 GB de espacio de disco desasignados. Con Windows 2008, puede utilizar el programa de utilidad de disco nativo para aumentar la partición primaria. Sin embargo, en Windows 2003 no existe esta capacidad nativa, por lo que se recomienda simplemente asignar el espacio.

### ¿Puedo utilizar BMR para mis copias de seguridad regulares?

No es una imagen de disco, sino un sistema de copia de seguridad de la imagen del volumen de disco. Este sistema no está pensado para que se utilice para copias de seguridad regulares, sino para que se utilice en combinación con estas.  

### ¿Puedo utilizar BMR para mis copias de seguridad de base de datos?

Las copias de datos de base de datos se deben realizar por separado, con los métodos normales de copia de seguridad de EVault. BMR no sustituye la necesidad de disponer de plugins de SQL o de Oracle. Aunque BMR utiliza la tecnología VSS para hacer copia de seguridad de archivos abiertos, no siempre podemos garantizar que los archivos copiados serán coherentes entre transacciones. Nuestra recomendación para estos tipos de aplicaciones especializadas es que se creen dos trabajos de copia de seguridad: uno para hacer copia de seguridad del sistema operativo y de los archivos binarios de aplicación y otro para los datos de aplicación. Encontrará una nota sobre este tema al final de la guía del usuario de BMR.

### ¿Qué tipo de trabajos de restauración puedo realizar con BMR?

Puede realizar una restauración completa del sistema o puede seleccionar archivos individuales de la copia de seguridad para restaurarlos. Esto significa que este trabajo puede sustituir el trabajo actual de copia de seguridad de archivos. El proceso de restauración se puede realizar dentro del sistema operativo, como si fuera un trabajo de copia de seguridad tradicional.

### ¿Tiene BMR capacidad de copia de seguridad de archivos abiertos?

BMR tiene capacidad de copia de seguridad de archivos abiertos. Sin embargo, BMR no sustituye la necesidad de disponer de plugins de SQL o de Oracle. Pulse [aquí](evault-mssql-plugin-installation.html) para ver instrucciones de instalación del plugin MSSQL.

### ¿Cuánto espacio de disco y tiempo requiere una restauración de BMR?

Una copia de seguridad realizada a partir de una instalación predeterminada utilizará unos 6 GB. Este tipo de restauración tardaría unos 15 minutos en un puerto de 1 GB. Este proceso también se ve afectado por la velocidad del puerto privado. Si necesita copias de seguridad o restauraciones más rápidas, quizás sea necesario aumentar la velocidad del puerto.
