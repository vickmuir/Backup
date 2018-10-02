---

copyright:
  years: 1994, 2018
lastupdated: "2018-08-15"

---
{:new_window: target="_blank"}

# Multivaulting (varias cajas fuertes)

Multivaulting es la capacidad de un cliente o servidor de conectar con más de una ubicación de EVault. Ofrece funciones de redundancia y la tranquilidad de saber que hay varias copias de seguridad disponibles, aunque uno de los sitios falle. 

**Puntos clave**

1. Se pueden gestionar varios EVaults a través del mismo WebCC y se manejan del mismo modo. La única diferencia es que el usuario dispone de varias opciones de caja fuerte.
2. La licencia del plugin es por caja fuerte: por ejemplo, si adquiere el plugin MSSQL para una caja fuerte en Washington DC, no funcionará en la caja fuerte de Seattle.
3. La nueva caja fuerte se tiene que añadir manualmente a WebCC tras cada adquisición.

**Ubicaciones de EVault Director**

La opción Multivaulting está disponible en todos los centros de datos y no existe ninguna limitación geográfica en la selección de una caja fuerte remota. Cuando las cajas fuertes se configuran siguiendo los pasos descritos en este documento, todas las cajas fuertes configuradas aparecen en los valores de caja fuerte.

>**Nota**: las copias de seguridad en ubicaciones de centros de datos remotos puede tardar más que las copias de seguridad en el mismo centro de datos en el que se encuentra el servidor.

## Adición de una caja fuerte remota a una cuenta

Debe añadir la nueva caja fuerte remota de EVault a la cuenta para que la nueva ubicación de copia de seguridad se pueda añadir en WebCC. 

1. Inicie una sesión en el [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}.
2. Pulse **Dispositivos**.
3. Localice y pulse el enlace correspondiente al servidor en cuestión.
4. En **Detalles del dispositivo**, pulse **Almacenamiento**.
5. Cuando se abra la sección Almacenamiento, desplácese hacia abajo hasta **EVault** y pulse **Añadir**.
6. En la ventana **Solicitar EVault**, seleccione la ubicación de la caja fuerte remota pulsando la lista desplegable.
7. Seleccione el tamaño del almacenamiento y pulse **Continuar**
8. Marque el recuadro **He leído el Maestro...** y pulse **Realizar pedido**.

La caja fuerte que acaba de solicitar se añade automáticamente a la cuenta. Si no es así, póngase en contacto con el equipo de ventas para obtener ayuda.
Cuando finalice el proceso de solicitud, vaya a **Almacenamiento** > **Copia de seguridad** para ver la nueva caja fuerte en la lista.

## Adición de una caja fuerte adicional en WebCC

1. Inicie una sesión en el [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} y pulse **Almacenamiento** > **Copia de seguridad** en el menú principal para visualizar los servidores con el servicio de copia de seguridad de EVault. 
2. Seleccione el servidor que desea que pueda realizar la copia de seguridad en varias cajas fuertes. Pulse la flecha que apunta hacia la derecha para visualizar el enlace WebCC.
3. Pulse el enlace **Inicio de sesión en WebCC** para iniciar el cliente WebCC en el navegador.
   >**Nota**: solo se puede acceder a WebCC a través de {{site.data.keyword.BluVPN}}.
4. En el panel de navegación de la izquierda, pulse **Todos los agentes**.
5. En la parte superior derecha, pulse **Editar** y seleccione **Valores de caja fuerte**.
6. En la ventana **Valores de caja fuerte**, pulse **Añadir**.
7. En la ventana **Nueva caja fuerte**:
  1. En el menú Perfil de caja fuerte, seleccione **Especificar valores de caja fuerte** para crear una nueva entrada. No actualice la entrada existente, ya que esto no funcionará.
  2. El nombre de caja fuerte no debe coincidir con ningún otro nombre de caja fuerte. Intente añadir al final del mismo la etiqueta -2. <br/> 
     >**Nota**: este campo tiene un límite de 15 caracteres.
  3. El campo de dirección IP contiene la información de ubicación de EVault Director. Por ejemplo, `ev-director301.service.softlayer.com` tiene la dirección IP 10.1.114.46 y se encuentra en WDC.
  4. En el campo de credenciales, especifique el ID de cuenta, el nombre de usuario de EVault para la caja fuerte seleccionada y la contraseña de la caja fuerte seleccionada.
  5. Pulse **Guardar cambios**.

En unos segundos se podrá utilizar la nueva caja fuerte. Si recibe un error de conexión, compruebe los valores y vuélvalo a intentar. Tenga en cuenta que la adición de una caja fuerte adicional solo le presenta un destino adicional que elegir para un trabajo. No ejecuta trabajos automáticamente sobre ambas cajas fuertes. Tiene que configurar los trabajos para que utilicen la caja fuerte adicional. Consulte la [Guía de aprendizaje de iniciación](index.html#getting-started-with-evault-backup-services) para ver instrucciones.
