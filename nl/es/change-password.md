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

# Cambio de la contraseña del servicio de copia de seguridad

Cada servicio de {{site.data.keyword.backup_full}} tiene una contraseña asociada que se utiliza para acceder a la caja fuerte dentro de WebCC.

Para muchos productos y servicios de {{site.data.keyword.BluSoftlayer_full}}, la característica de almacenamiento de contraseñas dentro del {{site.data.keyword.slportal}} solo se utiliza para realizar el seguimiento de las contraseñas. Para dichos productos y servicios, los cambios que se realizan en la contraseña dentro del {{site.data.keyword.slportal}} no se aplican al producto o servicio. **No** es el caso de {{site.data.keyword.backup_notm}}.

Los cambios que se realizan en la contraseña de copia de seguridad de IBM Cloud dentro del {{site.data.keyword.slportal}} se realizan en el propio servicio. Cuando cambie la contraseña, tenga en cuenta que afecta directamente a su servicio.
{:important}

## Cambio de la contraseña de IBM Cloud Backup

1. Inicie una sesión en la [consola de {{site.data.keyword.cloud_notm}}](https://{DomainName}/catalog/){:new_window} y pulse el icono **Menú** de la parte superior izquierda. Seleccione **Infraestructura clásica**.

   También puede iniciar la sesión en el [{{site.data.keyword.slportal}} ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://control.softlayer.com/){:new_window}.
2. Haga clic en **Almacenamiento** > **Copia de seguridad** para visualizar los servidores con servicio de copia de seguridad.
3. Pulse en cualquier lugar de la fila de la caja fuerte para ampliar la vista.
4. Pulse **Mostrar** para ver la contraseña actual.
5. Escriba la nueva contraseña en el campo **Contraseña**.
6. Pulse **Actualizar**.
