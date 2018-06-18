---

copyright:
  years: 1994, 2018
lastupdated: "2018-06-05"

---
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Configurar EVault en Windows 2016

Actualmente, WevCC de EVault no recibe soporte oficialmente en Windows 2016. Los servidores que se ejecutan en Windows 2016 deben utilizar el software Windows Central Control.

## Instalación del agente de copia de seguridad de EVault

1. En el servidor de destino, abra una sesión de navegador y especifique el siguiente URL para descargar el archivo ejecutable.
   ```
   http://downloads.service.softlayer.com/evault/
   ```
   {:pre}
2. Realice una doble pulsación en el archivo descargado y pulse **Ejecutar** en el recuadro emergente que aparece.
3. Seleccione el idioma de la instalación y pulse **Aceptar**.
4. Seleccione **Típica** como tipo de configuración. Pulse **Siguiente**.
5. En la pantalla para registrar el agente con el portal, seleccione **Omitir registro**. 
6. Pulse **Siguiente** y luego pulse **Finalizar**.

## Instalación del software CentralControl de EVault

1. En el servidor de destino, abra una sesión de navegador y especifique el siguiente URL para descargar el archivo ejecutable.

   ```
   http://downloads.service.softlayer.com/evault/CentralControl/
   ```
   {:pre}

2. Realice una doble pulsación en el archivo descargado y pulse **Ejecutar** en el recuadro emergente que aparece.
3. Siga los pasos de la instalación correspondientes a una configuración típica.

## Configuración de CentralControl

Esta tarea se lleva a cabo mediante una serie de interacciones con un usuario conectado al servidor designado para el servicio de copia de seguridad de EVault.

1. Controle de forma remota el servidor mediante RDP.
2. Inicie CentralControl.
3. En el espacio de trabajo, pulse con el botón derecho **Agente** y seleccione **Configuración del agente**.
4. Pulse **Nuevo**.
5. Seleccione **Registrar como un sistema nuevo** y pulse **Siguiente**.
6. Escriba la dirección de red y pulse **Añadir**; luego pulse **Siguiente**.
7. Escriba los nuevos valores de puerto y pulse **Añadir** y luego **Siguiente**.
8. En la pantalla de configuración de la conexión, escriba el número de segundos/minutos que desee. 
9. En la pantalla de autenticación, especifique sus credenciales y pulse **Siguiente**.
10. La ventana de sistemas registrados muestra el nombre de host de su servidor. Pulse **Siguiente**.
11.	Cuando el asistente de configuración de almacén haya terminado de recopilar su información, pulse **Finalizar** para completar el registro.


