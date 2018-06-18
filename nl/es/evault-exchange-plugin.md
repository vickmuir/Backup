---

copyright:
  years: 1994, 2018
lastupdated: "2018-06-06"

---
{:new_window: target="_blank"}

# Instalación del plugin EVault Exchange

El plugin Exchange se instala con el agente Windows en el host. Mediante el portal de WebCC puede configurar trabajos, hacer copia de seguridad de bases de datos Oracle en un almacén remoto seguro y restaurar bases de datos Oracle. El plugin Oracle se integra en la arquitectura existente.

## Funciones que se proporcionan

- Capacidad de hacer copia de seguridad y de restaurar bases de datos de Microsoft Exchange.

## Solicitar el plugin

1. Inicie una sesión en [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}.
2. Pulse **Almacenamiento** > **Copia de seguridad**.
3. Seleccione la cuenta de EVault y pulse **Solicitar plugins**.
4. Seleccione **Plugin de EVault - Exchange** y pulse **Continuar**.
5. Escriba su código de promoción si lo tiene y pulse **Recalcular**.
6. Se muestran los cargos actualizados. Revise el pedido.
7. Marque los recuadros para indicar que ha leído el Acuerdo de servicio maestro y que acepta los Términos de software de terceros. 
8. Pulse **Realizar pedido**.

## Instalar el plugin Exchange

El plugin Exchange se instala durante la instalación del agente Windows de 64 bits. El plugin se puede instalar al instalar el agente o se puede instalarse después, volviendo a ejecutar la instalación con la selección Modificar.

**Nota**: antes de instalar el plugin para el servidor Microsoft Windows, detenga ambos servicios de EVault en `services.msc`.  

1. Vaya a la carpeta `c:\installs\evault` y ejecute el archivo .exe con el número de revisión más alto.
2. En la pantalla de idioma pulse **Aceptar**
3. En la pantalla de bienvenida pulse **Siguiente**
4. Seleccione la opción **Modificar instalación** y pulse **Siguiente**.
5. Seleccione la opción **Dejar sin cambios** y pulse **Siguiente**.
6. En la pantalla de configuración personalizada, seleccione cada plugin que haya adquirido y seleccione **Esta característica se instalará en...**, luego pulse **Siguiente**.
7. Seleccione el botón **Conservar mi registro actual** y pulse **Siguiente**.
8. Pulse **Instalar**.
9. Una vez instalados, compruebe que ambos servicios están habilitados y en ejecución.
10. Si WebCC puede acceder (ver) a las bases de datos, significa que la instalación se ha realizado correctamente. 

## Guía del usuario

Conecte con la red de {{site.data.keyword.BluSoftlayer_full}} con {{site.data.keyword.BluVPN}} para poder descargar el archivo EVault Agent v8.0 for Microsoft Windows (64-bit) - Exchange Plug-in Guide.pdf de la [documentación descargable de EVault](http://downloads.service.softlayer.com/evault/Documentation/){:new_window}. En esta guía se describe cómo hacer copia de seguridad y restaurar bases de datos de Microsoft Exchange mediante el plugin Exchange. En esta guía también se describe cómo compartir un conjunto seguro de copias de seguridad DR para poder restaurar buzones específicos, mensajes u otros objetos en un archivo .pst utilizando la aplicación Granular Restore for Microsoft Exchange.


