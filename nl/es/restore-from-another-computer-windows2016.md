---

copyright:
  years: 1994, 2018
lastupdated: "2018-05-31"

---

# Restaurar un trabajo desde otro sistema en Windows 2016 

Este artículo contiene los pasos necesarios para realizar una restauración de archivos utilizando Evault Windows Central Control en Windows 2016 desde otro sistema. 

1. Controle de forma remota el servidor mediante RDP.
2. Abra CentralControl.
3. Pulse con el botón derecho en **Agente** y pulse **Configuración del agente**.
4. Elimine los valores de almacén actuales de CentralControl; para ello seleccione la entrada y pulse **Suprimir**.
5. Pulse **Nuevo** y, en la pantalla siguiente, seleccione **Volver a registrar sistema previamente registrado**. Pulse **Siguiente**
6. Escriba la dirección de red y pulse **Añadir**; luego pulse **Siguiente**.
7. Escriba los nuevos valores de puerto y pulse **Añadir** y luego **Siguiente**.
8. En la pantalla de configuración de la conexión, escriba el número de segundos/minutos que desee. 
9. En la pantalla de autenticación, especifique sus credenciales y pulse **Siguiente**.
10. La ventana de sistemas registrados muestra el nombre de host de su servidor. Pulse **Siguiente**.
11.	Cuando el asistente de configuración de almacén haya terminado de recopilar su información, pulse **Finalizar** para completar el registro.
12. Cuando se le solicite, confirme que desea continuar con el nuevo registro.
13. Cuando el registro finalice, pulse **Restaurar** en la barra de menús. 
9.	Seleccione el conjunto seguro adecuado y escriba la contraseña de cifrado. Pulse **Siguiente**.
10.	Seleccione los archivos que desea restaurar y seleccione las opciones predeterminadas; luego pulse **Finalizar**. 
11.	Cuando finalice la restauración, elimine el registro de almacén y vuelva a registrarse con la información de cuenta de almacén actual. 
