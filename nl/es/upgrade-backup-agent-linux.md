---

copyright:
  years: 1994, 2018
lastupdated: "2018-12-14"

---
{:new_window: target="_blank"}
{:pre: .pre}
{:tip: .tip}
{:note: .note}
{:important: .important}

# Actualización de Backup Software Agent para Linux

La versión más reciente del agente de {{site.data.keyword.backup_notm}} se puede descargar desde la sección de enlaces rápidos del panel de control del portal de {{site.data.keyword.backup_notm}}.
{:tip}

Seguir el proceso de actualización asegura que se puede actualizar el agente de {{site.data.keyword.backup_notm}} sin perder el registro.

1. Inicie sesión en el host a nivel raíz.
2. Descargue la versión más reciente del agente.
   ```
   wget -N downloads.service.softlayer.com/evault/Agent-Linux-x64-8.11.5251.tar.gz2
   ```
   {:pre}

3. Extraiga el contenido del archivo descargado.

   ```
   tar -xzvf Agent-Linux-x64-8.11.5251.tar.gz3
   ```
4. Vaya al directorio de instalación reciente.
   ```
   cd Agent-Linux-x64-8.11.5251/4.
   ```

5. Ejecute el script de instalación.
   ```
   ./install.sh
   ```
   {:pre}

6. Responda a las solicitudes seleccionando `N` para no registrar el sistema como nuevo host, seleccione el idioma y `A` para cifrar todos los datos mediante el Método de cifrado integrado.

7. Si la instalación tiene éxito, queda registrada en `/opt/BUAgent/Install.log`.
