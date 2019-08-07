---

copyright:
  years: 1994, 2019
lastupdated: "2019-08-01"

keywords: IBM Cloud backup, EVault, Carbonite, backup, reregister

subcollection: Backup

---
{:external: target="_blank" .external}
{:tip: .tip}
{:note: .note}
{:important: .important}

# Volver a registrar una caja fuerte
{: #reregister}

Esta tarea se suele realizar después de volver a cargar el sistema operativo de un servidor. También puede seguir estos pasos para [utilizar copias de seguridad de un servidor para restaurar datos en otro servidor](/docs/infrastructure/Backup?topic=Backup-restorefromotherVSI).
{:tip}

1. Inicie el portal de {{site.data.keyword.backup_notm}} e inicie una sesión. Para obtener más información, consulte la [Guía de aprendizaje Cómo empezar](/docs/infrastructure/Backup?topic=Backup-getting-started#getting-started).

   Recuerde que el portal de {{site.data.keyword.backup_notm}} solamente es accesible a través de {{site.data.keyword.BluVPN}}.
   {:tip}
2. Pulse **Todos los agentes**.
3. Mueva el ratón sobre **Editar**.
4. Seleccione **Valores de caja fuerte**.
5. Pulse **Volver a registrar**.
6. Complete el formulario.
  - Nombre de caja fuerte
  - Dirección de caja fuerte
  - Cuenta

    "Cuenta" es el equivalente del "Nombre de cuenta" en la [consola de {{site.data.keyword.cloud_notm}}](https://{DomainName}/classic/storage/backup){: external}. Generalmente tiene el formato "SLE[ID cuenta]"
    {:tip}
  - Nombre de usuario
  - Contraseña
7. Pulse **Cargar sistemas** y seleccione los sistemas que desea cargar.
8. Pulse **Guardar cambios**.
9. Renueve el sitio web para restaurar los trabajos de copia de seguridad anteriores.
10. Sincronice cada trabajo de copia de seguridad para restaurar el historial de conjuntos seguros.
11. Si los trabajos de copia de seguridad se han creado utilizando una contraseña de cifrado, debe especificar la contraseña de cifrado para restaurar los datos o continuar con las copias de seguridad.
12. Pulse **Cerrar**.
