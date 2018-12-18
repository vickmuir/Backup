---

copyright:
  years: 1994, 2018
lastupdated: "2018-12-14"

---
{:pre: .pre}
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Instalación del plugin de Oracle

El plugin Oracle es un complemento y se instala con el agente Windows o el agente Linux en el host de la base de datos Oracle. Mediante el portal de {{site.data.keyword.backup_notm}}, puede configurar trabajos, hacer copia de seguridad de bases de datos Oracle en una caja fuerte remota segura y restaurar bases de datos Oracle. El plugin Oracle se integra en la arquitectura existente.

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

1. Inicie una sesión en la [consola de {{site.data.keyword.cloud_notm}} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](https://{DomainName}/){:new_window} y pulse en el icono **Menú** de la parte superior izquierda. Seleccione **Infraestructura clásica**. <br/>
También puede iniciar la sesión en [{{site.data.keyword.slportal}} ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://control.softlayer.com/){:new_window} 
2. Haga clic en **Almacenamiento** > **Copia de seguridad** para visualizar los servidores con servicio de copia de seguridad.
3. Seleccione la cuenta y pulse **Solicitar plugins**.
4. Seleccione **Plugin de {{site.data.keyword.backup_notm}} - Oracle** y pulse **Continuar**.
5. Escriba su código de promoción, si lo tiene, y pulse **Recalcular**.
6. Se muestran los cargos actualizados. Revise el pedido.
7. Marque el recuadro para indicar que ha leído y que acepta los acuerdos de servicio de terceros.
8. Pulse **Realizar pedido**.

## Instalación del plugin de Oracle para Windows

El plugin Oracle para Windows se instala con el agente Windows de 32 o de 64 bits. Para instalar el plugin de Oracle, ejecute el kit de instalación del agente. El plugin Oracle aparece como una opción en la página **Configuración personalizada**.

Antes de instalar el plugin para el servidor Microsoft Windows, detenga ambos servicios de {{site.data.keyword.backup_notm}} en `services.msc`.
{:tip}

1. Vaya a la carpeta `c:\installs\evault` y ejecute el archivo .exe con el número de revisión más alto.
2. En la pantalla de idioma, pulse **Aceptar**
3. En la pantalla de bienvenida, pulse **Siguiente**
4. Seleccione la opción **Modificar instalación** y pulse **Siguiente**.
5. Seleccione la opción **Dejar sin cambios** y pulse **Siguiente**.
6. En la pantalla de configuración personalizada, seleccione cada plugin que haya adquirido y seleccione **Esta característica se instalará en...**; luego pulse **Siguiente**.
7. Seleccione **Conservar mi registro actual** y pulse **Siguiente**.
8. Pulse **Instalar**.
9. Una vez finalizada la instalación, asegúrese de que ambos servicios están habilitados y en ejecución.
10. Si el portal de {{site.data.keyword.backup_notm}} puede ver y acceder a la base de datos, significa que la instalación se ha realizado correctamente.

## Instalación del plugin de Oracle para Linux

El plugin Oracle es un complemento del agente Linux y se instala con el agente en el host de la base de datos. La aplicación de agente Linux debe estar instalada antes de instalar el plugin Oracle. El agente está disponible como una aplicación de 32 bits y de 64 bits. Para obtener más información, consulte [Instalación del cliente de copia de seguridad de {{site.data.keyword.backup_notm}} en Linux](install-backup-client-linux.html).

El kit de instalación del plugin Oracle está disponible en un archivo tar.gz.

1. En el host, descargue el paquete de instalación.
   ```
   http://downloads.softlayer.com/evault/Oracle-Plugin-Linux-x64-8.10.5249.tar.gz
   ```
   {: pre}

2. Extraiga los archivos del paquete.
   ```
   # cd /tmp
   # tar xvf Oracle-Plugin-Linux-x64-8.10.5249.tar
   ```
   {: pre}

3. Vaya a la carpeta.
   ```
   # cd Oracle-Plugin-Linux-x64-8.10.5249.xxxx
   ```
   {: pre}

4. Ejecute el script de instalación.
   ```
   # ./install.sh
   ```
   {: pre}

5. Siga las instrucciones de instalación que se muestran en pantalla.

El plugin de Oracle realiza una copia de seguridad de la base de datos completa "incoherente", que requiere que la base de datos se ejecute en modalidad ARCHIVELOG. DBA necesita asegurarse de que la base de datos esté en modalidad ARCHIVELOG antes de iniciar las copias de seguridad. Para obtener más información, consulte la Guía de usuario.
{:important}


## Descarga de la guía del usuario

Conéctese a la red de {{site.data.keyword.BluSoftlayer_full}} con {{site.data.keyword.BluVPN}} para poder descargar las guías del usuario desde la [Documentación descargable de {{site.data.keyword.backup_notm}}![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")](http://downloads.service.softlayer.com/evault/Documentation/){:new_window}
