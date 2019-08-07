---

copyright:
  years: 1994, 2019
lastupdated: "2019-08-01"

keywords: IBM Cloud backup, EVault, Carbonite, backup, multiple vaults, mulitple locations, disaster recovery

subcollection: Backup

---
{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Multivaulting (varias cajas fuertes)
{: #multivault}

Multivaulting es la capacidad de un cliente de conectar un servidor con más de una ubicación de caja fuerte. Ofrece redundancia y tranquilidad porque hay varias copias de seguridad disponibles, aunque uno de los sitios falle.

**Puntos clave**

1. Se pueden gestionar varias cajas fuertes a través del mismo portal de {{site.data.keyword.backup_notm}} y se manejan del mismo modo. La única diferencia es que el usuario dispone de varias opciones de caja fuerte.
2. La licencia del plugin es por caja fuerte: por ejemplo, si adquiere el plugin MSSQL para una caja fuerte en Washington DC, no funcionará en la caja fuerte de Seattle.
3. La nueva caja fuerte se tiene que añadir manualmente al portal de {{site.data.keyword.backup_notm}} tras cada adquisición.



**Ubicaciones del Director de cajas fuertes de {{site.data.keyword.backup_notm}}**

El multivaulting está disponible en todos los centros de datos y no hay limitación geográfica en la selección de una caja fuerte remota. Cuando las cajas fuertes se configuran correctamente, todas las cajas fuertes configuradas aparecen en los valores de caja fuerte.

Las copias de seguridad en ubicaciones de centros de datos remotos puede tardar más que las copias de seguridad en el mismo centro de datos en el que se encuentra el servidor.
{:note}

## Adición de una caja fuerte remota a una cuenta

Debe añadir la nueva caja fuerte remota a la cuenta para que la nueva ubicación de copia de seguridad se pueda añadir en el portal de {{site.data.keyword.backup_notm}}.
{:important}

1. Inicie la sesión en la [consola de {{site.data.keyword.cloud_notm}}](https://{DomainName}){: external}. En el menú de navegación, seleccione **Infraestructura clásica**.
2. Pulse **Dispositivos**.
3. Localice y pulse el enlace correspondiente al servidor en cuestión.
4. En **Detalles del dispositivo**, pulse **Almacenamiento**.
5. Cuando se abra la sección Almacenamiento, desplácese hacia abajo hasta **{{site.data.keyword.backup_notm}}** y pulse **Añadir**.
6. En la ventana **Solicitar {{site.data.keyword.backup_notm}}**, seleccione la ubicación de la caja fuerte remota pulsando la lista desplegable.
7. Seleccione el tamaño del almacenamiento y pulse **Continuar**
8. Marque el recuadro **He leído el Maestro...** y pulse **Realizar pedido**.

La caja fuerte que acaba de solicitar se añade automáticamente a la cuenta. Si no es así, póngase en contacto con el equipo de ventas para obtener ayuda.

Cuando finalice el proceso de solicitud, vaya a **Almacenamiento** > **Copia de seguridad** para ver la nueva caja fuerte en la lista.

## Adición de una caja fuerte adicional en el portal de {{site.data.keyword.backup_notm}}

1. Inicie la sesión en la [consola de {{site.data.keyword.cloud_notm}}](https://{DomainName}){: external}. En el menú de navegación, seleccione **Infraestructura clásica**.
2. Pulse **Almacenamiento** > **Copia de seguridad en cloud** para visualizar los servidores con servicio de copia de seguridad.
3. Seleccione el servidor que desea que pueda realizar la copia de seguridad en varias cajas fuertes. Pulse la flecha para revelar el enlace del portal de {{site.data.keyword.backup_notm}}.
4. Pulse el enlace de **inicio de sesión en el portal de {{site.data.keyword.backup_notm}}** para iniciar el cliente del portal en su navegador.

   Solo se puede acceder al portal de {{site.data.keyword.backup_notm}} a través de {{site.data.keyword.BluVPN}}.
   {:tip}
5. En el panel de navegación, pulse **Todos los agentes**.
6. Pulse **Editar** y seleccione **Valores de caja fuerte**.
7. En la ventana **Valores de caja fuerte**, pulse **Añadir**.
8. En la ventana **Nueva caja fuerte**:
  1. En el menú Perfil de caja fuerte, seleccione **Especificar valores de caja fuerte** para crear una nueva entrada. No actualice la entrada existente, ya que esto no funcionará.
  2. El nombre de caja fuerte no debe coincidir con ningún otro nombre de caja fuerte. Intente añadir al final del mismo una etiqueta `-2`. <br/>

     El campo de nombre de la caja fuerte tiene un límite de 15 caracteres.
     {:important}
  3. El campo de dirección IP contiene la información de ubicación de {{site.data.keyword.backup_notm}} Director. Por ejemplo, `ev-director301.service.softlayer.com` tiene la dirección IP 10.1.114.46 y se encuentra en WDC.
  4. En el campo de credenciales, especifique el ID de cuenta, el nombre de usuario de {{site.data.keyword.backup_notm}} para la caja fuerte seleccionada y la contraseña de la caja fuerte seleccionada.
  5. Pulse **Guardar cambios**.

En unos segundos se podrá utilizar la nueva caja fuerte. Si recibe un error de conexión, compruebe los valores y vuélvalo a intentar. Tenga en cuenta que la adición de una caja fuerte adicional le presenta un destino adicional que elegir para un trabajo. No ejecuta trabajos automáticamente sobre ambas cajas fuertes. Tiene que configurar los trabajos para que utilicen la caja fuerte adicional. Para obtener más información, consulte la [Guía de aprendizaje Cómo empezar](/docs/infrastructure/Backup?topic=Backup-getting-started#getting-started).
