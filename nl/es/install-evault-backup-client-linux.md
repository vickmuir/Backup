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

# Instalación del cliente de copia de seguridad de EVault en Linux 

La instalación del cliente de copia de seguridad de EVault en un sistema operativo basado en Linux se puede realizar mediante una serie de mandatos en el shell o terminal en el sistema operativo. En este procedimiento se describen los pasos a seguir para instalar el cliente de copia de seguridad de EVault en cualquiera de los siguientes sistemas operativos basados en Linux:

- RedHat Enterprise Linux
- CentOS
- CloudLinux

Después de completar el procedimiento, el proceso automatizado registrará el servicio del agente con WebCC y luego descargará e instalará los archivos necesarios para ejecutar el servicio. Siga los pasos siguientes para instalar el cliente de copia de seguridad de EVault en su sistema operativo basado en Linux.

**Nota**: si ha adquirido EVault al solicitar un servidor en el {{site.data.keyword.slportal}}, el software se instala automáticamente y no necesita seguir los procedimientos que se describen en este documento.

Si ha adquirido EVault como una actualización en el {{site.data.keyword.slportal}}, siga estos pasos para instalar el software.

## Inicie una sesión en el servidor del dispositivo de destino

1. Inicie una sesión en el {{site.data.keyword.slportal}} de [](https://control.softlayer.com/){:new_window} y seleccione **Dispositivos** > **Lista de dispositivo** en el menú principal para ver los dispositivos de servidor disponibles.
2. Busque el dispositivo para el que ha adquirido el servicio de EVault y anote su dirección IP pública. Se utilizará en los siguientes pasos cuando se inicie una sesión en el dispositivo desde una línea de mandatos de UNIX o Linux. Sustituya <direcciónIPPública> por la dirección IP pública real en los mandatos siguientes. 
3. Pulse la flecha de expansión que apunta a la derecha para visualizar información sobre el dispositivo, incluido el nombre de usuario y la contraseña.  Si no se muestra la contraseña, pulse el recuadro de selección **Mostrar contraseña** para verla. El nombre de usuario y la contraseña se utilizará en el paso siguiente para iniciar una sesión en el dispositivo de prueba.  Sustituya `<user name>` por el nombre de usuario real en los mandatos siguientes.
4. Inicie una sesión en el dispositivo de destino mediante ssh y ejecute el mandato siguiente desde una línea de mandatos de Unix o Linux:
  ```
  ssh <nombre usuario>@<direcciónIPPública>
  ```
  {: pre}
  
 **Nota**: si nunca ha iniciado una sesión en este servidor con este nombre de usuario, aparecerá un mensaje con información sobre la autenticidad del host y se le preguntará si desea continuar.  Responsa **sí** para continuar.
5. Se le solicitará que especifique la contraseña a menos que haya configurado previamente claves ssh para acceder a este servidor.

## Actualice Linux para prepararlo para instalar el cliente de EVault (solo RedHat Linux)
**Nota**: este paso es obligatorio para RedHat Linux, pero opcional para otras distribuciones de Linux.

- Ejecute el mandato siguiente en el indicador del servidor:
  ```
  yum update
  ```
  {: pre}
   
  Si se le solicita, confirme que el tamaño de descarga es correcto. La actualización continuará y mostrará el mensaje "Completado" cuando termine.

## Obtenga el script de instalación de EVault
- Ejecute el mandato siguiente en el indicador del servidor:
  ```
  wget -N http://downloads.service.softlayer.com/evault/evault_manual.sh
  ```
  {: pre}
   
## Ejecute el script de instalación de EVault
1. Ejecute el mandato siguiente en el indicador del servidor:
  ```
  sh ./evault_manual.sh
  ```
  {: pre}

2. Escriba su nombre de usuario y contraseña de WebCC.     
  **Nota**: consulte el artículo sobre [Iniciación a los servicios de copia de seguridad](/docs/infrastructure/Backup/index.html) para obtener instrucciones sobre cómo ver el nombre de usuario y la contraseña de EVaultbackup.
3. Después del nombre de usuario y de la contraseña, no se necesita ninguna otra información de entrada, aunque verá algunas solicitudes escritas en la pantalla a medida que continúe la instalación. Estas solicitudes se pueden pasar por alto tranquilamente. Las genera un subscript al que invoca el script *evault_manual.sh*.  El script *evault_manual.sh* genera la entrada para estas solicitudes.
4. Cuando aparezca un mensaje parecido al siguiente, significa que se ha completado la instalación:
  ```
  Starting VVAgent: [  OK  ]
  Starting buagent: [  OK  ]
  ```
  {: codeblock}
   
## Verifique que la instalación se ha realizado correctamente
1. Verifique que aparece el mensaje "Registrado en el portal." en la información de salida de la instalación. Para ello busque el mensaje en la pantalla o examine la información de salida del siguiente mandato:
  ```
  grep 'Registered'  /opt/BUAgent/Install.log
  ```
  {: pre}

2. Ejecute el mandato siguiente y observar la información de salida: 
  ```
  service vvagent status
  ```
  {: pre}
   
  Deberían aparecer los siguientes mensajes:
  ```
  VVAgent is running (PID xxxxx).
  buagent is running (PID xxxxx).
  ```
  {: codeblock}
   
  **Nota**: los ID de proceso representados arriba mediante 'xxxxx' variarán con cada instalación. 
  
## Siguientes pasos

Inicie una sesión en WebCC para configurar y gestionar los agentes de copia de seguridad. Consulte la [Guía de aprendizaje de iniciación](index.html#configuring-evault-agent-in-webcc) para ver instrucciones.
