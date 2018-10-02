---

copyright:
  years: 1994, 2018
lastupdated: "2018-08-13"

---
{:pre: .pre}
{:new_window: target="_blank"}

# Configuración de EVault en Windows 2016

## Instalación de EVault Software Agent

1. En el servidor de destino, abra una sesión de navegador y especifique el siguiente URL para descargar el archivo ejecutable.
   ```
   http://downloads.service.softlayer.com/evault/
   ```
   {:pre}
   >**Nota**: Instale el agente versión 8.30 y posterior.
2. Realice una doble pulsación en el archivo descargado y pulse **Ejecutar** en la ventana que aparece.
3. Seleccione el idioma de la instalación y pulse **Aceptar**.
4. Pulse **Siguiente** para comenzar.
5. Lea los términos y condiciones y seleccione **Acepto los términos del acuerdo de licencia**. A continuación, pulse **Siguiente**.
6. Seleccione **Típica** como tipo de configuración. Pulse **Siguiente**.
7. En la pantalla para registrar el agente con el portal, seleccione **Omitir registro**. Pulse **Siguiente**
8. En la pantalla siguiente, pulse **Instalar**.
9. Cuando termine la instalación, pulse **Finalizar**.

## Instalación de EVault Software CentralControl 8.30

1. En el servidor de destino, abra una sesión de navegador y especifique el siguiente URL para descargar el archivo ejecutable.

   ```
   http://downloads.service.softlayer.com/evault/CentralControl/
   ```
   {:pre}

2. Realice una doble pulsación en el archivo descargado y pulse **Ejecutar** en la ventana que aparece.
3. Siga los pasos de instalación correspondientes a una configuración **Típica**.
   1. Cuando se le solicite que añada un acceso directo de escritorio, seleccione **Sí**. Pulse **Siguiente**.
   2. Después de leer el acuerdo de licencia de software, seleccione **ACEPTAR**. Pulse **Siguiente**.
   3. Mantenga la carpeta de destino predeterminada y pulse **Siguiente**.
4. Cuando finalice la instalación, marque **Iniciar EVault Software Central Control**. Pulse **Finalizar**.


## Configuración de CentralControl

Esta tarea se lleva a cabo mediante una serie de interacciones con un usuario conectado al servidor designado para el servicio de copia de seguridad de EVault.

1. Controle de forma remota el servidor mediante RDP.
2. Inicie CentralControl.
3. En el espacio de trabajo, pulse con el botón derecho en **MyAgent** y seleccione **Configuración del agente**.
4. En el separador Cajas fuertes, pulse **Nueva**. Aparece el asistente para la configuración de la caja fuerte. Pulse **Siguiente**.
5. Seleccione **Registrar como un sistema nuevo** y pulse **Siguiente**.
6. Especifique el nombre de caja fuerte en el campo Nombre de perfil. Puede obtener el nombre de caja fuerte del [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}.
6. Escriba la dirección de red (la dirección IP de la caja fuerte asignada) y pulse **Añadir**. A continuación, pulse **Siguiente**.
7. Escriba los nuevos valores de puerto y pulse **Añadir** y luego **Siguiente**.
8. En la pantalla de configuración de la conexión, escriba el número de segundos/minutos que desee. Mantenga marcado el recuadro **Habilitar cifrado sobre cable para transmisiones a/desde la caja fuerte**. Pulse **Siguiente**.
9. En la pantalla de autenticación, especifique sus credenciales y pulse **Siguiente**.
10. La ventana de sistemas registrados muestra el nombre de host de su servidor. Pulse **Siguiente**.
11.	Pulse **Finalizar** para completar la configuración.


## Creación de esquemas de retención de EVault

1. Controle de forma remota el servidor mediante RDP.
2. Inicie CentralControl.
3. En el espacio de trabajo, pulse con el botón derecho en **MyAgent** y seleccione **Configuración del agente**.
4. Pulse el separador **Retenciones**. Cuando aparezca el asistente para retención, pulse **Siguiente**.
5. Escriba el nombre de la retención. Pulse **Siguiente**.<br/>
   **Nota**: la entrada puede tener un máximo de 32 caracteres alfanuméricos. No se permiten espacios, pero se pueden utilizar signos de subrayado (`_`) y guiones (`-`).
6. Escriba los días de retención en línea y las copias para este tipo de retención. A continuación, pulse **Siguiente**.<br/>
   **Nota**: la combinación de días de retención y copias se utiliza para garantizar que se retienen un número mínimo de copias de seguridad durante una duración mínima.
7. Seleccione **No deseo crear ninguna copia de seguridad de archivado**. Pulse **Siguiente**.
8. Pulse **Finalizar** para completar la configuración del esquema de retención.


## Configuración del trabajo de EVault

1. Controle de forma remota el servidor mediante RDP.
2. Inicie CentralControl.
3. En el espacio de trabajo, pulse con el botón derecho en **MyAgent** y seleccione **Nuevo trabajo**. 
4. En la pantalla de bienvenida, pulse **Siguiente**.
5. Seleccione el tipo de origen de copia de seguridad.
6. Seleccione **Unicode** para codificar. Pulse **Siguiente**.
7. Seleccione el destino de este trabajo. Pulse **Siguiente**.
8. Escriba el nombre del trabajo y su descripción.<br/>
   **Nota**: el nombre debe tener entre 1 y 30 caracteres de longitud. El nombre puede contener letras, números, signos de subrayado (`_`), guiones(`-`) y símbolos de dólar (`$`).
9. Seleccione los orígenes de datos. Pulse **Añadir**.
10. Especifique las opciones de proceso y de tiempo de copia de seguridad. Marque **Exploración rápida de archivos** y escriba las horas o minutos que desea como ventana de tiempo de la copia de seguridad. A continuación, pulse **Siguiente**.
11. Seleccione el tipo de cifrado (el valor predeterminado es AES de 256 bits) y especifique la contraseña de cifrado. Pulse **Siguiente**
12. Seleccione las opciones de registro para el trabajo. Marque **Crear archivo de registro** y seleccione **Depurar automáticamente solo archivos de registro caducados**. A continuación, pulse **Siguiente**
13. Seleccione **Solo salir de este asistente** y pulse **Finalizar** para completar la configuración. Ahora el nuevo trabajo aparece bajo MyAgent.


## Ejecución del trabajo de EVault

1. Controle de forma remota el servidor mediante RDP.
2. Inicie CentralControl.
3. En el espacio de trabajo, pulse con el botón derecho en **MyAgent** y seleccione el agente que ha creado.
4. En la pantalla de bienvenida, pulse **Siguiente**.
5. Seleccione el destino de copia de seguridad o una ubicación alternativa para inicializar el trabajo de copia de seguridad. Pulse **Siguiente**.<br/>
   *Consejo*: para obtener más información sobre varias cajas fuertes, consulte [Multivaulting (varias cajas fuertes)](multivaulting.html)
6. Seleccione la opción Exploración rápida de archivos para no leer los archivos que no se han modificado. Pulse **Siguiente**.
7. Pulse **Finalizar** para completar la configuración e iniciar la copia de seguridad. Aparece una ventana de información del proceso que muestra el estado del trabajo de copia de seguridad. Cuando finalice el trabajo de copia de seguridad, pulse **Cerrar**.
