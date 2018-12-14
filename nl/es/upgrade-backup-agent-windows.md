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

# Actualización de Backup Software Agent para Windows

Utilice estas instrucciones paso a paso para actualizar el agente de {{site.data.keyword.backup_notm}} en un servidor Windows.

1. Controle de forma remota el servidor {{site.data.keyword.BluSoftlayer_full}} que requiere una actualización de {{site.data.keyword.backup_notm}} mediante RDP.
2. Abra un navegador y vaya a la siguiente dirección.
   ```
   http://downloads.service.softlayer.com/evault/
   ```
   {:pre}
3. Pulse el archivo que desee. (Por ejemplo, Agent-Windows-x64-6-72-1072a.exe)

   El número de versión está en el nombre del archivo. Elija el más reciente. <br/>Hay instaladores distintos para 32 bits y para 64 bits. Si tiene un sistema operativo de 64 bits, descargue el archivo que contiene x64 en su nombre.
   {:tip}
4. Pulse **Ejecutar** en la pantalla de descarga y pulse otra vez después de que se descargue.
5. Pulse **Sí** para actualizar **EVault Software Agent**.

   Es posible que el instalador desaparezca durante un minuto mientras se carga.
   {:note}
6. Seleccione **Conservar mi registro actual** y pulse **Siguiente**.
7. Pulse **Siguiente**. El agente comienza el proceso de actualización. Puede tardar unos minutos.
8. En la pantalla de finalización, pulse **Finalizar**.
