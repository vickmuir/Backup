---

copyright:
  years: 1994, 2019
lastupdated: "2019-04-01"

keywords: IBM Cloud Backup, VMware, VRA, vSphere Recovery Agent, plug-in, plugin, EVault, Carbonite, vSphere

subcollection: Backup

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Restauración de datos de vSphere
{: #VRARestore}
 
Cuando las VM están protegidas en un entorno de vSphere, puede restaurar [las VM de vSphere](#restoreVMs) y [restaurar archivos y carpetas](#restoreFFVRA) con vSphere Recovery Agent.

## Restauración de VM de vSphere
{: #restoreVMs}

1.	En la barra de navegación, pulse **Sistemas**. Aparece una cuadrícula con una lista de los sistemas disponibles. 
2.	Busque el entorno de vSphere con la VM que desea restaurar y expanda la vista pulsando en la fila. 
3.	Pulse **Trabajos**. 
4.	Busque el trabajo de copia de seguridad con la VM que desea restaurar y pulse **Restaurar** en el menú **Seleccionar acción**. 
5.	En el recuadro de diálogo **Seleccione lo que desea restaurar**, seleccione **Máquinas virtuales**. 
6.	Pulse **Continuar**. El diálogo Restaurar muestra el conjunto seguro más reciente del trabajo. 
    * Para restaurar datos desde otro origen, pulse en un origen (caja fuerte) de la lista **Dispositivo de origen**. 
    *	Para restaurar desde un conjunto seguro anterior, pulse el botón **Examinar conjuntos seguros**. En el calendario que aparece, pulse la fecha de los conjuntos seguros desde los que desee restaurar. 
7.	En el panel **Elementos a restaurar**, seleccione las VM que desee restaurar. 
8.	En el campo **Contraseña de cifrado**, escriba la contraseña de cifrado de datos. 
9.	En la lista **Almacén de datos de destino**, seleccione el almacén de datos para las VM restauradas. 
10.	Seleccione una de las siguientes opciones para restaurar las VM en el almacén de datos que ha seleccionado:
  * **Restaurar todas las máquinas virtuales seleccionadas únicamente al almacén de datos seleccionado.**
  * **Restaurar al almacén de datos seleccionado solo cuando el almacén de datos original de la máquina virtual no esté disponible.** Si la VM de la que se ha hecho copia de seguridad contiene varios VMDK que residían en dos o más almacenes de datos, y uno o más de estos almacenes de datos no están disponibles, se restaura la VM completa al almacén de datos seleccionado. 

  Si restaura una VM o una plantilla a un vCenter y la VM original está presente, la VM se restaura como un clon de la original con el nombre siguiente: <nombreVM>-vra-restored-<Date>. La VM se restaura como un clon si la VM original está encendida, apagada o suspendida. Si está encendida y utiliza una dirección IP estática, puede encontrarse con un conflicto de direcciones IP cuando se encienda la VM clonada.
  {:note}

13.	En la lista **Host de destino**, pulse en el host donde desea registrar las VM. En la lista solo se muestran los hosts que tienen acceso al almacén de datos seleccionado.
14.	Seleccione una de las siguientes opciones para registrar las VM restauradas en los hosts que ha seleccionado: 
  * **Registrar todas las máquinas virtuales seleccionadas únicamente en los hosts seleccionados.**
  * **Registrar en los hosts seleccionados solos si el host original de la máquina virtual no está disponible.**
15.	Para encender las VM una vez que se han restaurado, seleccione **Encender las VM tras restaurarlas**. 
16.	En **Opciones de rendimiento**, deje el valor predeterminado. 
17.	Pulse **Ejecutar restauración**.

## Restauración de archivos y carpetas
{: #restoreFFVRA}

Puede restaurar archivos y carpetas desde una VM de Windows protegida utilizando vSphere Recovery Agent (VRA). Puede restaurar archivos y carpetas desde más de una VM a la vez. No puede restaurar archivos y carpetas desde una VM de Linux con VRA.
{:important}

Durante una restauración de archivos y carpetas, se montan los volúmenes desde la VM seleccionada como unidades en la máquina donde se está ejecutando VRA. A continuación, puede compartir algunas o todas las unidades montadas de forma que los usuarios puedan copiar archivos y carpetas de las unidades. También puede iniciar sesión en la máquina de VRA y copiar archivos y carpetas desde las unidades montadas. 

Los archivos y carpetas de los discos están accesibles para cualquiera en el sistema de VRA, incluyendo los usuarios no administradores. Si le preocupa la seguridad, puede proteger la máquina agente e impedir que los usuarios inicien sesión en la máquina localmente.
{:tip}

1. En la barra de navegación, pulse **Sistemas**. Aparece una cuadrícula con una lista de los sistemas disponibles.
2. Busque el entorno de vSphere con la VM que desea restaurar y expanda la vista pulsando en la fila.
3. Pulse **Trabajos**. 
4. Busque el trabajo de copia de seguridad con la VM que desea restaurar y pulse **Restaurar** en el menú **Seleccionar acción**.
5. En el diálogo **Seleccione lo que desea restaurar**, seleccione **Archivos y carpetas**.
6. Pulse **Continuar**. El diálogo Restaurar muestra el conjunto seguro más reciente del trabajo. 
  * Para restaurar datos desde otro recurso, pulse origen en la lista Dispositivo de origen (caja fuerte).
  * Para restaurar desde un conjunto seguro anterior, pulse el botón Examinar conjuntos seguros. En el calendario que aparece, pulse la fecha del conjunto seguro desde el que desee restaurar. A la derecha del calendario, pulse el conjunto seguro desde el que desee restaurar. 
7. En el panel **Elementos a restaurar**, seleccione la VM con los archivos y carpetas que desee restaurar. 
8. En el campo **Contraseña de cifrado**, especifique la contraseña de cifrado de datos. 
9. En el **campo Tiempo de inactividad**, especifique el número de minutos de inactividad tras los cuales la unidad compartida pasa automáticamente a dejar de estar compartida. El tiempo de inactividad puede ir de 2 a 180 minutos. 
    
    La unidad no deja de estar compartida mientras se estén copiando datos. Si copia los mismos datos desde una unidad compartida más de una vez, el sistema podría agotar el tiempo de espera porque no se están leyendo datos nuevos.
    {:note}
    
10.	En **Opciones de rendimiento**, seleccione Utilizar todo el ancho de banda disponible. 
11.	Pulse **Ejecutar restauración**. 
12. Los volúmenes restaurados de la VM seleccionada se correlacionan como unidades en la máquina donde se está ejecutando VRA y están disponibles en una carpeta del Montaje de restauración.  Realice uno de los siguientes pasos.
  * Copie los archivos y carpetas que desee restaurar desde las unidades correlacionadas. 
  * Comparta una o más unidades correlacionadas con otros usuarios. A continuación, los usuarios pueden acceder a la unidad compartida UNC y copiar los archivos y carpetas que deseen restaurar. 
  * Comparta uno o más directorios desde la carpeta del Montaje de restauración en la máquina VRA. A continuación, los usuarios pueden acceder a la unidad compartida UNC y copiar los archivos y carpetas que deseen restaurar. 
