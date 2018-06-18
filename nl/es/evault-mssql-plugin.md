---

copyright:
  years: 1994, 2018
lastupdated: "2018-06-06"

---
{:new_window: target="_blank"}

# Instalación del plugin EVault SQL Server

El plugin SQL Server se instala con el agente de Windows en el host de la base de datos SQL. Mediante el portal de WebCC puede configurar trabajos, hacer copia de seguridad de bases de datos SQL en un almacén remoto seguro y restaurar bases de datos SQL.

## Funciones que se proporcionan

- Puede ejecutar copias de seguridad completas de bases de datos, copias de seguridad completas de bases de datos con registros de transacciones o copias de seguridad solo de registros de transacciones.
- Puede ejecutar varias copias de seguridad a la vez. 
- Puede restaurar bases de datos SQL en la misma instancia de SQL o en otra instancia de SQL,
- Puede restaurar bases de datos con los nombres de base de datos originales, sobrescribir las bases de datos existentes y restaurar utilizando la opción de no recuperación.

## Solicitar el plugin

1. Inicie una sesión en el {{site.data.keyword.slportal}}{:new_window} de [
2. Pulse Almacenamiento > Copia de seguridad.
3. Seleccione la cuenta de EVault y pulse Solicitar plugins.
4. Seleccione Plugin de EVault - MSSQL y pulse Continuar.
5. Escriba su código de promoción si lo tiene y pulse Recalcular.
6. Se muestran los cargos actualizados. Revise el pedido.
7. Marque los recuadros para indicar que ha leído el Acuerdo de servicio maestro y que acepta los Términos de software de terceros. 
8. Pulse Realizar pedido.

## Instalar el plugin MSSQL

Para instalar el plugin SQL para Windows, ejecute el kit de instalación del agente. El plugin aparece como una opción en la página Configuración personalizada.

Nota: antes de instalar el plugin MSSQL EVault para el servidor Microsoft Windows, detenga ambos servicios de EVault en services.msc.

1. Vaya a la carpeta c:\installs\evault y ejecute el archivo .exe con el número de revisión más alto.
2. En la pantalla de idioma pulse Aceptar.
3. En la pantalla de bienvenida, pulse Siguiente.
4. Seleccione la opción Modificar instalación y pulse Siguiente.
5. Seleccione la opción Dejar sin cambios y pulse Siguiente.
6. En la pantalla de configuración personalizada, seleccione cada plugin que haya adquirido y seleccione Esta característica se instalará en..., luego pulse Siguiente.
7. Seleccione el botón Conservar mi registro actual y pulse Siguiente.
8. Pulse Instalar.
9. Una vez instalados, compruebe que ambos servicios están habilitados y en ejecución.
10. Si WebCC puede acceder (ver) a las bases de datos, significa que la instalación se ha realizado correctamente. 

## Guía del usuario

Conecte con la red de {{site.data.keyword.BluSoftlayer_full}} con {{site.data.keyword.BluVPN}} para poder descargar el archivo EVault Agent for Microsoft Windows v8.0 - SQL Server Plug-in Guide.pdf de la [documentación descargable de EVault](http://downloads.service.softlayer.com/evault/Documentation/)(https://control.softlayer.com/)]{:new_window}.

## Preguntas más frecuentes

### ¿Qué hace VSS (Volume Shadow Copy Services)?

La versión actual del plugin de SQL Server utiliza VSS (Volume Shadow Copy Services) para hacer copias de seguridad. El plugin de SQL Server que utiliza VSS hace copias de seguridad eficientes de bases de datos SQL, de bases de datos SQL que abarcan varios volúmenes, permite que se realicen copias de seguridad mientras las aplicaciones siguen escribiendo en un volumen y ofrece coherencia de datos dentro de las bases de datos y entre las mismas. VSS permite ejecutar varias copias de seguridad a la vez.

### ¿Cuáles son las principales características del plugin de SQL?

- Posibilidad de especificar los nombres de las bases de datos para incluirlas y excluirlas en trabajos de copia de seguridad de SQL Server mediante caracteres comodín (asteriscos y signos de interrogación). Las bases de datos nuevas con nombres que coinciden con los filtros de un trabajo de copia de seguridad se incluyen o excluyen automáticamente cuando se ejecuta el trabajo. 
- Posibilidad de proteger las bases de datos secundarias en grupos de disponibilidad AlwaysOn utilizando el agente de 64 bits y el plugin de SQL Server.
- Posibilidad de compartir conjuntos seguros de SQL que contienen bases de datos con contenido SharePoint 2010/2013 para utilizarlos con la aplicación Granular Restore for Microsoft SharePoint. Una vez compartido un conjunto seguro, se puede utilizar la aplicación Granular Restore para restaurar colecciones de sitios, sitios web, bibliotecas, carpetas, elementos de lista o documentos.
- Soporte de copia de seguridad que admite delta de bases de datos situadas en volúmenes distribuidos.
Posibilidad de proteger las bases de datos en el modelo de recuperación completa con una sola entrada de planificación. Esta opción permite proteger las bases de datos y gestionar el truncamiento de registros de transacciones en una sola entrada de planificación.
- El plugin de SQL Server da soporte a copias de seguridad completas, completas que incluyen registros de transacciones y de registros de transacciones (terminología actualizada coherente con la terminología de SQL Server). EVault seguirá dando soporte a la función Single Pass Restore, que permite al cliente seleccionar una copia de seguridad de "registro de transacciones" en un punto en el tiempo. EVault restaurará las bases de datos completas y todos los registros de transacciones necesarios para restaurar la base de datos en el punto en el tiempo seleccionado.
- Un trabajo de copia de seguridad puede contener una o varias bases de datos de la misma instancia de SQL Server. Se puede crear otro trabajo para hacer copia de seguridad de otras bases de datos de otra instancia de SQL Server que, si se desea, se puede ejecutar simultáneamente.
- Posibilidad de restaurar bases de datos con la opción "sin recuperación" para proporcionar opciones adicionales de recuperación mediante SQL Server Management Studio.
- Opción de restauración alternativa que da soporte a la restauración en archivos, lo que permite al administrador de bases de datos montar las bases de datos mediante SQL System Manager.
- La restauración alternativa incluye la posibilidad de dirigir la restauración de una base de datos a otra, incluso cuando los nombres lógicos de las bases de datos no coinciden. En el caso de objetos no coincidentes, el plugin creará las bases de datos en la ubicación de base de datos predeterminada de la instancia.
- Soporte de Transparent Data Encryption (TDE) con SQL Server 2008 R2 (SP1) de 64 bits y SQL Server 2012.
- Si un host SQL Server se pierde por completo, se puede instalar el software SQL Server y se puede restaurar por completo la base de datos. (Primero se debe restaurar la base de datos maestra.)
- Una vez iniciada la copia de seguridad, la copia se realiza con o sin los servicios de base de datos en ejecución.
- Las restauraciones se pueden realizar con los nombres originales de base de datos (con o sin sobrescritura de las bases de datos existentes), sobre una base de datos existente o en archivos de disco.

