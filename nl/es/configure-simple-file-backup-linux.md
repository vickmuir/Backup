---

copyright:
  years: 1994, 2018
lastupdated: "2018-05-14"

---
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Configuración de una copia de seguridad simple a nivel de archivo en Linux

Después de haber solicitado el servicio EVault y de haber instalado el agente en el servidor, puede empezar a crear copias de seguridad de los datos. El artículo contiene los pasos a seguir para configurar el agente, planificar la retención y empezar su primer trabajo de copia de seguridad.

## Iniciar WebCC

1. Inicie una sesión en el {{site.data.keyword.slportal}} de [](https://control.softlayer.com/){:new_window} y pulse **Almacenamiento** > **Copia de seguridad** en el menú principal para visualizar los servidores con el servicio de copia de seguridad de EVault. 
2. Seleccione el servidor donde residen los archivos de los que va a hacer copia de seguridad. Pulse la flecha de expansión que apunta a la derecha para visualizar el enlace WebCC.
3. Inicie la conexión VPN para acceder a la red privada de IBM.
4. Pulse el enlace de inicio de sesión de WebCC para iniciar el cliente WebCC en el navegador.<br/>
  **Nota**: si WebCC no se inicia, es posible que haya un problema con la conexión VPN. También puede ver un mensaje que indique que el método de envío no es seguro. Esto es normal; continúe con el envío del formulario.
  
## Configurar un trabajo de copia de seguridad

1. En el panel de navegación de la izquierda, pulse **Todos los agentes** para visualizar los agentes actuales de EVault
2. Pulse **Este es un nuevo agente que me gustaría configurar**.
3. Escriba un nombre de trabajo y una descripción de trabajo para el trabajo que va a configurar o crear.
4. Para **Tipo de origen de copia de seguridad**, seleccione el tipo de sistema de archivos del que desea realizar la copia de seguridad en el menú desplegable.
5. Pulse **Siguiente** para continuar. 
6. En el panel **Archivos de datos**, vaya a los archivos y directorios que desea incluir en la copia de seguridad pulsando los símbolos **+** y **-** que hay junto a los iconos de carpeta.
7. Marque los recuadros de selección que hay junto a los archivos y directorios que desea incluir y luego pulse **Incluir** para guardar las selecciones.
8. Puede filtrar sus selecciones utilizando la pantalla emergente que aparece o pulsar **Aceptar** para utilizar las selecciones que ha realizado tal como están. <br /> Después de haber incluido sus selecciones de archivos y directorios, los archivos y directorios seleccionados se muestran en el panel **Conjunto de copia de seguridad** en la parte derecha de la pantalla. Puede repetir los pasos 6 - 8 para añadir más archivos o para eliminar archivos que haya incluido (mediante el botón **Excluir**). También puede utilizar el botón **Eliminar** para suprimir cualquier elemento de línea del panel **Conjunto de copia de seguridad**. Cuando esté satisfecho con la configuración del conjunto de copia de seguridad, pulse **Siguiente** para continuar.
9. Seleccione el tipo de cifrado que desea. 
  - Si no desea cifrar la copia de seguridad, seleccione **Ninguno**.   
  - Si desea cifrado, seleccione **AES de 256 bits** y especifique una contraseña en los campos Contraseña y Verificar contraseña. Si lo desea, puede añadir una clave de contraseña. <br/> **Nota**: necesitará esta contraseña para restaurar los archivos de la copia de seguridad. No hay forma de recuperar una contraseña perdida ni de restaurar una copia de seguridad cifrada sin conocer la contraseña.   
10. Si desea utilizar alguna de las **Opciones avanzadas**, aquí encontrará una explicación de cada opción:
  - **Retención** le ayuda a gestionar el uso de los datos. El periodo de retención determina el tiempo que se conservará una copia de seguridad. Una vez transcurrido el periodo de retención, la copia de seguridad se eliminará automáticamente. Las opciones integradas son diaria, semanal o mensual.
  - **Compresión** se utiliza para reducir la cantidad de capacidad utilizada para guardar copias de seguridad.
La opción para hacer copia de seguridad de archivos abiertos para escritura permite hacer una copia de seguridad de los archivos, aunque los tenga abiertos una aplicación cuando se ejecute el trabajo de copia de seguridad.
  - **Crear archivo de registro** le permite crear y gestionar el contenido y la retención de los archivos de registro que se generan durante el proceso de copia de seguridad. 
  - **Copia de seguridad de una sola instancia de todos los archivos con enlace fijo seleccionados**. Esta opción solo se aplica a los sistemas de tipo unix. Si utiliza enlaces fijos para crear varios nombres de archivos para cierto contenido, esta opción genera una sola copia del contenido que se va a guardar. Tras la restauración, se restauran todos los enlaces fijos. Esta opción requiere una exploración previa de la selección de archivos, lo que puede ocupar una cantidad significativa de tiempo y de memoria.
11. Después de realizar su selección de cifrado, pulse **Siguiente** para continuar en la pantalla **Crear una planificación**.   
12. En la página Crear una planificación, pulse **Añadir** para planificar un trabajo de copia de seguridad basado en tiempo o pulse **Siguiente** para crear un trabajo manual.
  - Si elige crear un trabajo manual, continúe en el Paso 15.
  - Si elige planificar un trabajo basado en tiempo, seleccione los días y la hora del día en que desea ejecutar las copias de seguridad.
  - Seleccione el esquema de retención. [Aquí](evault-backup-faq.html#how-do-the-retention-schemes-work-) encontrará más información sobre los esquemas de retención
  - Pulse **Opciones avanzadas de planificación** para ver más opciones de configuración, si lo desea. Puede seleccionar **Utilizar aplazamiento* para evitar que se ejecutan copias de seguridad de gran tamaño durante horas de mucha actividad en la red. Si el aplazamiento está habilitado, el trabajo de copia de seguridad no hace copia de seguridad de los datos nuevos después del periodo de tiempo especificado y confirma el conjunto seguro en el almacén, aunque no se haya hecho copia de seguridad de algunos datos en el trabajo. Los cambios en los datos de los que ya se había hecho copia de seguridad anteriormente se copiarán, independientemente del periodo de tiempo especificado. <br/> Cuando se vuelve a ejecutar el trabajo, el agente comprueba si hay cambios en los datos que se habían copiado anteriormente, hace copia de seguridad de dichos cambios y luego hace copia de seguridad de los datos restantes.  Si un trabajo de copia de seguridad se aplaza mientras se está haciendo copia de seguridad de un elemento (por ejemplo archivo, base de datos, volumen, vSphere VMDK o Hyper-V VM), la copia de seguridad de dicho elemento queda incompleta y los datos del elemento no se pueden restaurar. Sin embargo, puede restaurar los elementos que se habían copiado anteriormente en el trabajo antes de que se aplazara el trabajo.
13. Después de haber configurado la planificación de copia de seguridad, pulse **Aceptar** para guardarla. El trabajo planificado se añade a la lista de trabajos planificados. 
  - Puede repetir el paso 12 para planificar copias de seguridad adicionales. 
  - Para realizar cambios en un trabajo de copia de seguridad existente, seleccione el trabajo pulsando su fila y luego pulse **Editar** y realice los cambios.
14. Seleccione un almacén para el trabajo de seguridad y pulse **Guardar cambios**.
15. Ejecute un trabajo de copia de seguridad
  - Si ha planificado un trabajo de copia de seguridad basado en tiempo, no hay pasos adicionales.  El trabajo se ejecutará automáticamente según lo planificado.
  - Si ha configurado un trabajo manual (sin una planificación basada en tiempo), puede ejecutarlo seleccionando su fila en la lista de trabajos y pulsando **Ejecutar copia de seguridad**. <br/> Al igual que sucede con los trabajos basados en tiempo, puede elegir el Esquema de retención y las Opciones avanzadas de copia de seguridad. Después de completar las opciones de configuración, pulse **Iniciar copia de seguridad** para iniciar el trabajo.
