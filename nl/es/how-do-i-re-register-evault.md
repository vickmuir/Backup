---

copyright:
  years: 1994, 2018
lastupdated: "2018-05-30"

---
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}

# Registro de un EVault

Esta tarea suele ser un paso necesario después de volver a cargar el sistema operativo de un servidor, pero también puede seguir estos pasos para [utilizar copias de seguridad de un servidor para restaurarlas en otro servidor](restore-from-another-computer.html).

1. Inicie sesión como usuario en WebCC. Consulte [Iniciación a los servicios de copia de seguridad](/docs/infrastructure/Backup/index.html) para ver instrucciones. Recuerde que solo se puede acceder a WebCC a través de {{site.data.keyword.BluVPN}}.

2. En la parte izquierda, pulse **Todos los agentes**.

3. En la esquina superior derecha, mueva el ratón sobre **Editar**.

4. Seleccione **Valores de almacén**.

5. Pulse **Volver a registrar**.

6. Especifique esta información: 
  - Nombre de almacén
  - Dirección de almacén
  - Cuenta
  - Nombre de usuario
  - Contraseña. <br/>
  **Nota**: "Cuenta" equivale a "Nombre de usuario" en la página [Iniciación a los servicios de copia de seguridad](index.html). Generalmente tiene el formato "SLE[ID cuenta]"

7. Pulse **Cargar sistemas** y seleccione los sistemas que desea cargar.

8. Pulse **Guardar cambios**.

9. Renueve el sitio web para restaurar los trabajos de copia de seguridad anteriores.

10. Sincronice cada trabajo de copia de seguridad para restaurar el historial de conjuntos seguros. 

11. Si los trabajos de copia de seguridad se han creado utilizando una contraseña de cifrado, debe especificar la contraseña de cifrado para restaurar los datos o continuar con las copias de seguridad.

12. Pulse **Cerrar** y habrá terminado.
