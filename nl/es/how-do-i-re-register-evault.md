---

copyright:
  years: 1994, 2018
lastupdated: "2018-06-26"

---
{:new_window: target="_blank"}

# Registro de un EVault

Esta tarea se suele realizar después de volver a cargar el sistema operativo de un servidor. También puede seguir estos pasos para [utilizar copias de seguridad de un servidor para restaurar datos en otro servidor](restore-from-another-computer.html).

1. Inicie WebCC e inicie una sesión. Consulte [Iniciación a los servicios de copia de seguridad](/docs/infrastructure/Backup/index.html) para ver instrucciones. <br/>Recuerde que solo se puede acceder a WebCC a través de {{site.data.keyword.BluVPN}}.

2. En la parte izquierda, pulse **Todos los agentes**.

3. En la parte superior derecha, mueva el ratón sobre **Editar**.

4. Seleccione **Valores de almacén**.

5. Pulse **Volver a registrar**.
 
6. Complete el formulario.
  - Nombre de almacén
  - Dirección de almacén
  - Cuenta <br/>**Nota**: "Cuenta" es el equivalente de "Nombre de cuenta" en el [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}. Generalmente tiene el formato "SLE[ID cuenta]"
  - Nombre de usuario
  - Contraseña

7. Pulse **Cargar sistemas** y seleccione los sistemas que desea cargar.

8. Pulse **Guardar cambios**.

9. Renueve el sitio web para restaurar los trabajos de copia de seguridad anteriores.

10. Sincronice cada trabajo de copia de seguridad para restaurar el historial de conjuntos seguros.

11. Si los trabajos de copia de seguridad se han creado utilizando una contraseña de cifrado, debe especificar la contraseña de cifrado para restaurar los datos o continuar con las copias de seguridad.

12. Pulse **Cerrar**.
