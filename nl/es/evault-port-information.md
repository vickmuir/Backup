---

copyright:
  years: 1994, 2018
lastupdated: "2018-05-30"

---
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}

# Información sobre puertos de EVault

El agente EVault instalado en el servidor debe ser capaz de comunicarse con el almacén que ha adquirido. Encontrará información sobre el host de EVault Director correspondiente a una cuenta de usuario de EVault en el portal del cliente. Registre siempre los agentes en los directores de WebCC y de EVault mediante FQDN, ya que las IP correspondientes a estos servicios pueden cambiar. 

Los servidores se deben comunicar con WebCC y con todos los servidores proxy AMP para que WebCC funcione correctamente, independientemente de la ubicación del centro de datos: evregister.service.softlayer.com TCP 8086,8087. 

Se pueden añadir servidores proxy AMP adicionales si se necesitan para poder gestionar más agentes EVault registrados en WebCC. 

TCP Puerto 8086, 8087 debería tener acceso a 10.0.0.0/8. 

Si necesita utilizar reglas de cortafuegos más restrictivas, es posible que pierda el acceso a WebCC a medida que se amplía la infraestructura. Actualmente sus servidores deberían permitir como mínimo el acceso a las subredes 10.0.82.0/24 y 10.2.118.0/24 para los puertos TCP 8086, 8087. En el futuro se pueden utilizar subredes adicionales si se necesitan.

## Comercial:

### Servidores proxy WebCC y AMP:

- ev-webcc01.service.softlayer.com [10.0.82.12] 8086, 8087
- evregister.service.softlayer.com [10.0.82.12] 8086, 8087

### Servidores proxy AMP comerciales:

- evwebamp0901.service.softlayer.com [10.2.118.12] 8087
- evwebamp0902.service.softlayer.com [10.2.118.13] 8087
- evwebamp0903.service.softlayer.com [10.2.118.14] 8087
- evwebamp0904.service.softlayer.com [10.2.118.15] 8087
- evwebamp0905.service.softlayer.com [10.2.118.16] 8087
- evwebamp0906.service.softlayer.com [10.2.118.17] 8087
- evwebamp0907.service.softlayer.com [10.2.118.18] 8087
- evwebamp0908.service.softlayer.com [10.2.118.19] 8087

## Federal:

### Proxy WebCC y AMP:

- webcc.service.usgov.softlayer.com [100.100.6.20] 8086, 8087
 
El agente debe permitir el tráfico de entrada en el puerto TCP/2548 en la red privada. Esto permite que CentralControl y WebCC se conecten al agente para gestionarlo. Las versiones antiguas de EVault utilizaban el puerto 808.

El puerto de gestión de EVault (2548) se puede modificar actualizando la clave de registro en:HKLM\SOFTWARE\EVault\InfoStage\Agent\AgentPortNumber (que es un dword) en sistemas operativos Windows.

**Aclaración adicional**: la diferencia entre utilizar CentralControl de escritorio y el agente en lo referente a valores de conexión suele ser confusa. El agente residente en el servidor se conecta a nuestros servidores EVault, mientras que CentralControl utilizado en el escritorio se suele conectar a su servidor, utilizando esta dirección y las credenciales del servidor para acceder al mismo.
