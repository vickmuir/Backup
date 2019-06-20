---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-05"

keywords: IBM Cloud backup, EVault, Carbonite, backup, port information, configure, configuring,

subcollection: Backup

---
{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Configuración de puertos para permitir la comunicación entre el agente de copia de seguridad y el portal de {{site.data.keyword.backup_notm}}
{: #portinfo}

El agente de {{site.data.keyword.backup_full}} instalado en el servidor debe ser capaz de comunicarse con la caja fuerte que ha adquirido. Encontrará información sobre el host de Director para una cuenta de usuario de {{site.data.keyword.backup_notm}} en la [consola de {{site.data.keyword.cloud_notm}}](https://{DomainName}/classic/storage/backup){: external}.

Registre siempre los agentes en el portal de {{site.data.keyword.backup_notm}} y en los directores utilizando el nombre de dominio totalmente calificado, ya que las direcciones IP correspondientes a estos servicios pueden cambiar.

Los servidores se deben comunicar con el portal de {{site.data.keyword.backup_notm}} y con todos los servidores proxy AMP para que el portal de {{site.data.keyword.backup_notm}} funcione correctamente, independientemente de la ubicación del centro de datos.

```
https://evregister.service.softlayer.com TCP 8086,8087
```

Se pueden añadir servidores proxy AMP adicionales si se necesitan para poder gestionar más agentes {{site.data.keyword.backup_notm}} registrados en el portal de {{site.data.keyword.backup_notm}}.

El puerto TCP 8086, 8087 debería tener acceso a 10.0.0.0/8.
{:important}

Si necesita utilizar reglas de cortafuegos más restrictivas, es posible que pierda el acceso al portal de {{site.data.keyword.backup_notm}} a medida que se amplía la infraestructura. Actualmente sus servidores deberían permitir como mínimo el acceso a las subredes 10.0.82.0/24 y 10.2.118.0/24 para los puertos TCP 8086, 8087. En el futuro se pueden utilizar subredes adicionales si se necesitan.

## Comercial

*Servidores proxy AMP y de portal de {{site.data.keyword.backup_notm}}*

- `https://ev-webcc01.service.softlayer.com` [10.0.82.12] 8086, 8087
- `https://evregister.service.softlayer.com` [10.0.82.12] 8086, 8087

*Servidores proxy AMP comerciales*

- evwebamp0901.service.softlayer.com [10.2.118.12] 8087
- evwebamp0902.service.softlayer.com [10.2.118.13] 8087
- evwebamp0903.service.softlayer.com [10.2.118.14] 8087
- evwebamp0904.service.softlayer.com [10.2.118.15] 8087
- evwebamp0905.service.softlayer.com [10.2.118.16] 8087
- evwebamp0906.service.softlayer.com [10.2.118.17] 8087
- evwebamp0907.service.softlayer.com [10.2.118.18] 8087
- evwebamp0908.service.softlayer.com [10.2.118.19] 8087

## Federal

*Proxy AMP y portal de {{site.data.keyword.backup_notm}}*

- webcc.service.usgov.softlayer.com [100.100.6.20] 8086, 8087

El agente debe permitir el tráfico de entrada TCP en el puerto 2548 en la red privada. Este valor permite que Central Control y el portal de {{site.data.keyword.backup_notm}} se conecten al agente para gestionarlo. Las versiones antiguas de EVault utilizaban el puerto 808.

El puerto de gestión de {{site.data.keyword.backup_notm}} (2548) se puede modificar actualizando la clave de registro de: `HKLM\SOFTWARE\EVault\InfoStage\Agent\AgentPortNumber` (que es una `dword`) en los sistemas operativos Windows.

Cuando se trata de valores de conexión, la diferencia entre Central Control de escritorio y el agente suele ser un punto de confusión. El agente residente en el servidor se conecta a los servidores de {{site.data.keyword.backup_notm}}, mientras que Central Control utilizado por el escritorio se conecta a su servidor utilizando su dirección y las credenciales del servidor para acceder al mismo.
{:tip}
