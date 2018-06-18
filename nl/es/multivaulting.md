---

copyright:
  years: 1994, 2018
lastupdated: "2018-05-31"

---
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Multivaulting (varios almacenes)

Multivaulting es la capacidad de un cliente o servidor de conectar con más de una ubicación de EVault. Ofrece funciones de redundancia y la tranquilidad de saber que hay varias copias de seguridad disponibles, aunque uno de los sitios falle. 

## Puntos clave

1. Se pueden gestionar varios EVaults a través del mismo WebCC y se manejan del mismo modo. La única diferencia es que el usuario dispone de varias opciones de almacén.
2. La licencia del plugin es por almacén: por ejemplo, si adquiere una licencia de un EVault para el plugin MSSQL en Washington DC, no funcionará en el almacén de Seattle.
3. El nuevo EVault se tiene que añadir manualmente a WebCC tras cada pedido.

## Adición de un almacén remoto a una cuenta

Debe añadir el nuevo almacén remoto de EVault a la cuenta para que la nueva ubicación de copia de seguridad se pueda añadir en WebCC. 

1. Inicie una sesión en el {{site.data.keyword.slportal}}{:new_window} de [
2. Pulse Dispositivos
3. Localice y pulse el enlace correspondiente al servidor en cuestión.
4. En Detalles del dispositivo, pulse Almacenamiento
5. Cuando se abra la sección Almacenamiento, desplácese hacia abajo hasta EVault y pulse Añadir
6. En el recuadro de diálogo Solicitar EVault que se abre, seleccione la ubicación del almacén remoto pulsando el menú desplegable.
7. Seleccione el tamaño del almacenamiento y pulse Continuar
8. Marque el recuadro He leído el Maestro... y pulse Realizar pedido.

El almacén que acaba de solicitar se añade automáticamente a la cuenta. Si no es así, póngase en contacto con el equipo de ventas para obtener ayuda.
Cuando finalice el proceso de solicitud, vaya a Almacenamiento > Copia de seguridad para ver el nuevo almacén en la lista.

## Adición de un almacén adicional a WebCC

1. Inicie una sesión en el {{site.data.keyword.slportal}} de [](https://control.softlayer.com/)(https://control.softlayer.com/)]{:new_window} y pulse Almacenamiento > Copia de seguridad en el menú principal para visualizar los servidores con el servicio de copia de seguridad de EVault. 
2. Seleccione el servidor donde residen los archivos que desea restaurar. Pulse la flecha de expansión que apunta a la derecha para visualizar el enlace WebCC.
3. Pulse el enlace de inicio de sesión de WebCC para iniciar el cliente WebCC en el navegador. <br/>**Nota**: solo se puede acceder a WebCC a través de {{site.data.keyword.BluVPN}}.
4. En el panel de navegación de la izquierda, pulse **Todos los agentes**.
5. En la esquina superior derecha, pulse **Editar** y seleccione **Valores de almacén**.
6. En la ventana **Valores de almacén", pulse **Añadir**.
7. En el recuadro de diálogo **Nuevo almacén**:
  1. En el menú desplegable Perfil de almacén, seleccione **Especificar valores de almacén** para crear una nueva entrada. No actualice la entrada existente, ya que esto no funcionará.
  2. El nombre de almacén no debe coincidir con ningún otro nombre de almacén. Recomendamos añadir al final del mismo la etiqueta -2. <br/> **Nota**: este campo tiene un límite de 15 caracteres.
  3. El campo de dirección IP se completa con información de ubicación de evdirector. Por ejemplo, ev-director301.service.softlayer.com tiene la dirección IP 10.1.114.46 y está situado en WDC. Consulte la parte inferior de la página para ver otras direcciones y ubicaciones de EVault Director.
  4. En el campo de credenciales, la cuenta será el ID de cuenta del cliente, el nombre de usuario será el nombre de usuario de EVault correspondiente al almacén seleccionado y la contraseña será la contraseña del almacén seleccionado.
  5. Pulse **Guardar cambios**.

En unos segundos podrá utilizar el nuevo almacén. Si recibe un error de conexión, compruebe los valores y vuélvalo a intentar. Tenga en cuenta que la adición de un almacén adicional solo le presenta un destino adicional que elegir para un trabajo; no ejecuta trabajos automáticamente sobre ambos almacenes. Tiene que configurar los trabajos para que utilicen el almacén adicional. Consulte la [Guía de aprendizaje de iniciación](index.html#getting-started-with-evault-backup-services) para ver instrucciones.

## Ubicaciones de EVault Director

La opción Multivaulting está disponible en todos los centros de datos y no existe ninguna limitación geográfica en la selección de un almacén remoto. Cuando los almacenes se configuran siguiendo los pasos descritos en este documento, todos los almacenes configurados aparecen en los valores de almacén.

**Nota**: las copias de seguridad en ubicaciones de centros de datos remotos puede tardar más que las copias de seguridad en el mismo centro de datos en el que se encuentra el servidor.

