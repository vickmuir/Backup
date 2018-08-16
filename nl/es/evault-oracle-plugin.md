---

copyright:
  years: 1994, 2018
lastupdated: "2018-07-02"

---
{:new_window: target="_blank"}

# Instalación del plugin Oracle de EVault

El plugin Oracle se instala en el agente Windows en el host de la base de datos Oracle. Mediante el portal de WebCC, puede configurar trabajos, hacer copia de seguridad de bases de datos Oracle en un almacén remoto seguro y restaurar bases de datos Oracle. El plugin Oracle se integra en la arquitectura existente.

**Funciones que se proporcionan**

- Soporte para copia de seguridad y recuperación de bases de datos Oracle.
- El plugin Oracle ofrece copias de seguridad no RMAN basadas en ARCHIVELOG de instancias completas de bases de datos en línea. Se hace una copia de seguridad automática de todos los espacios de tablas y archivos de parámetros de instancias que no son temporales. Oracle Corporation recomienda realizar las copias de seguridad en periodos de baja actividad de bases de datos.
- Las bases de datos completas y parciales se restauran mediante los mecanismos normales de recuperación de Oracle gestionados por el usuario.

**Limitaciones**
- Solo se hace copia de seguridad de las bases de datos locales, de una sola instancia y basadas en disco.
- No se hace copia de seguridad de los clústeres de bases de datos.
- No se hace copia de seguridad de los dispositivos en bruto.
- No se hace copia de seguridad de las bases de datos remotas.
- La base de datos se debe ejecutar en modalidad ARCHIVELOG y el usuario bajo el que se ha configurado la copia de seguridad debe tener privilegios SYSDBA.
- Las contraseñas de las bases de datos se cifran para mejorar la seguridad sobre los métodos basados en script.

## Solicitud del plugin

1. Inicie una sesión en [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}.
2. Pulse **Almacenamiento** > **Copia de seguridad**.
3. Seleccione la cuenta de EVault y pulse **Solicitar plugins**.
4. Seleccione **Plugin de EVault - Oracle** y pulse **Continuar**.
5. Escriba su código de promoción, si lo tiene, y pulse **Recalcular**.
6. Se muestran los cargos actualizados. Revise el pedido.
7. Marque el recuadro para indicar que ha leído y que acepta los acuerdos de servicio de terceros. 
8. Pulse **Realizar pedido**.

## Instalación del plugin Oracle

El plugin Oracle para Windows se instala con el agente Windows de 32 o de 64 bits. Para instalar el plugin Oracle para Windows, ejecute el kit de instalación del agente. El plugin Oracle aparece como una opción en la página **Configuración personalizada**.

>**Nota**: antes de instalar el plugin para el servidor Microsoft Windows, detenga ambos servicios de EVault en `services.msc`.  

1. Vaya a la carpeta `c:\installs\evault` y ejecute el archivo .exe con el número de revisión más alto.
2. En la pantalla de idioma, pulse **Aceptar**
3. En la pantalla de bienvenida, pulse **Siguiente**
4. Seleccione la opción **Modificar instalación** y pulse **Siguiente**.
5. Seleccione la opción **Dejar sin cambios** y pulse **Siguiente**.
6. En la pantalla de configuración personalizada, seleccione cada plugin que haya adquirido y seleccione **Esta característica se instalará en...**; luego pulse **Siguiente**.
7. Seleccione **Conservar mi registro actual** y pulse **Siguiente**.
8. Pulse **Instalar**.
9. Una vez finalizada la instalación, asegúrese de que ambos servicios están habilitados y en ejecución.
10. Si WebCC puede acceder/ver la base de datos, significa que la instalación se ha realizado correctamente. 

## Descarga de la guía del usuario

Conecte con la red de {{site.data.keyword.BluSoftlayer_full}} con {{site.data.keyword.BluVPN}} para poder descargar el archivo EVault Agent v8.0 for Microsoft Windows - Oracle plug-in Guide.pdf de la [documentación descargable de EVault](http://downloads.service.softlayer.com/evault/Documentation/){:new_window}.




