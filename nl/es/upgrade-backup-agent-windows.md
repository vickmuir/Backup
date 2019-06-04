---

copyright:
  years: 1994, 2019
lastupdated: "2019-02-05"

keywords: IBM Cloud backup, EVault, Carbonite, backup, upgrade agent, Windows

subcollection: Backup

---
{:pre: .pre}
{:tip: .tip}
{:note: .note}
{:important: .important}

# Actualización de Backup Software Agent para Windows
{: #UpgradeinWindows}

La versión más reciente del agente de copia de seguridad se puede descargar desde la sección de enlaces rápidos del panel de control del portal de {{site.data.keyword.backup_notm}}.
{:tip}

1. Controle de forma remota el servidor {{site.data.keyword.cloud}} que requiere una actualización de {{site.data.keyword.backup_notm}}.
2. Abra un navegador y vaya a la siguiente dirección.
   ```
   http://downloads.service.softlayer.com/evault/
   ```
   {:pre}
3. Pulse el archivo que desee. (Por ejemplo, Agent-Windows-x64-6-72-1072a.exe)

   El número de versión está en el nombre del archivo. Elija el más reciente. <br/>{{site.data.keyword.cloud}} ofrece distintos instaladores de 32 bits y de 64 bits. Si tiene un sistema operativo de 64 bits, descargue el archivo que contiene x64 en su nombre.
   {:tip}
4. Pulse **Ejecutar** en la pantalla de descarga y pulse otra vez después de que se descargue.
5. Pulse **Sí** para actualizar **{{site.data.keyword.backup_notm}} Software Agent**.

   Es posible que el instalador desaparezca durante un minuto mientras se carga.
   {:note}
6. Seleccione **Conservar mi registro actual** y pulse **Siguiente**.
7. Pulse **Siguiente**. El agente comienza el proceso de actualización. Puede tardar unos minutos.
8. En la pantalla de finalización, pulse **Finalizar**.
