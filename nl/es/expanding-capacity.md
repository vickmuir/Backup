---

copyright:
  years: 1994, 2018
lastupdated: "2018-12-14"

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Ampliación de la capacidad de la caja fuerte

Los usuarios actuales de {{site.data.keyword.BluSoftlayer_full}} pueden ampliar el tamaño de su caja fuerte hasta un máximo de 4000 GB. No es necesario que creen un duplicado ni que migren los datos manualmente a un volumen más grande. No hay interrupción ni falta de acceso a la caja fuerte mientras el aumento del límite entra en vigor.

## Solicitud de un aumento

1. Inicie una sesión en la [consola de {{site.data.keyword.cloud_notm}}](https://{DomainName}/catalog/){:new_window} y pulse el icono **Menú** de la parte superior izquierda. Seleccione **Infraestructura clásica**.

   También puede iniciar la sesión en el [{{site.data.keyword.slportal}} ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://control.softlayer.com/){:new_window}.
2. Haga clic en **Almacenamiento** > **Copia de seguridad** para visualizar los servidores con servicio de copia de seguridad.
3. Seleccione la caja fuerte que desea ampliar.
4. Pulse **Acciones** y seleccione **Modificar {{site.data.keyword.backup_notm}}**.
5. En la pantalla siguiente, seleccione el nuevo tamaño y pulse **Actualizar**.

## Facturación

Los datos de facturación del volumen se actualizan automáticamente para añadir al ciclo de facturación la diferencia prorrateada del nuevo precio. Luego se factura el nuevo importe completo durante el siguiente ciclo de facturación.

Se puede utilizar el mismo proceso para reducir el tamaño de {{site.data.keyword.backup_notm}}.
{:tip}
