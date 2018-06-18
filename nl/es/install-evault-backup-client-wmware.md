---

copyright:
  years: 1994, 2017
lastupdated: "2017-10-03"

---
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}

# Instalación del cliente de copia de seguridad de EVault para VMware

La instalación del cliente de copia de seguridad de EVault en un servidor VMware se puede realizar mediante una serie de mandatos en el shell o terminal en el servidor ESX de destino. En este procedimiento se describen los pasos a seguir para instalar el cliente de copia de seguridad de EVault en el servidor VMware:

Para instalar el agente, descargue y copie el paquete `Agent-VMware-ESX-Server-6.71.<version-info>.tar.gz` en el servidor ESX de destino con el siguiente mandato:

`wget -N http://downloads.service.softlayer.com/evault/archive/Agent-VMware-ESX-Server-6.71.2105.tar.gz`

**Nota**: debe realizar los pasos siguientes localmente en el servidor ESX de destino.

1. Extraiga los archivos del paquete. Para hacerlo, utilice este mandato (en el que “PACKAGENAME” podría ser “Agent-VMware-ESX-Server-6.71”):
    `tar xvfz PACKAGENAME.tar.gz`
2. Vaya al directorio en el que ha extraído el paquete.
3. Ejecute el script de instalación:
    `# ./install.sh`

    **Nota**: el script de instalación le solicitará de forma interactiva información de configuración, como datos sobre el registro web (dirección, número de puerto y autenticación) y el nombre del archivo de registro.
     
    - Especifique el nombre de usuario WebCC correspondiente a este servidor.
    - Especifique la contraseña WebCC correspondiente a este servidor.
     
4. Especifique el **Nombre de usuario de copia de seguridad de EVault** como entrada para el indicador que le solicita el nombre de usuario de WebCC. 
5. Especifique la **Contraseña de copia de seguridad de EVault** como entrada para el indicador que le solicita la contraseña de WebCC.
6. Cuando finalice la instalación, aparecerá un mensaje de finalización y se ejecutará el daemon del agente.


### Otras notas sobre la instalación:
El archivo Install.log estará en el directorio de instalación si esta se ha ejecutado correctamente.
Por ejemplo: `/opt/BUAgent/Install.log`

Si la instalación falla y se retrotrae, el registro de instalación estará en el `<Installation Failure directory>`.
Si falla pero no se retrotrae, el registro de instalación estará en el `<Installation Kit directory>`.

Para obtener más información, descargue el archivo [VMware_Agent_User_Guide](http://downloads.service.softlayer.com/evault/Documentation/VMware_Agent_User_Guide.pdf){:new_window}. Asegúrese de estar conectado a {{site.data.keyword.BluVPN}} para poder ver este enlace.
