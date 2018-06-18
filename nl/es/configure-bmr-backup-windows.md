---

copyright:
  years: 1994, 2018
lastupdated: "2018-05-31"

---
{:new_window: target="_blank"}

# Configuración de un trabajo de copia de seguridad de BMR en Windows

## Requisito previo

Debe adquirir el plugin BMR para realizar una copia de seguridad de BMR. BMR solo está disponible para servidores nativos Windows. La opción BMR no está disponible para VSI.

## Iniciar WebCC
**Nota**: debe estar conectado a la red privada de {{site.data.keyword.BluSoftlayer_full}} para poder iniciar WebCC.
1. Inicie una sesión en el {{site.data.keyword.slportal}} de [](https://control.softlayer.com/){:new_window} y pulse **Almacenamiento** > **Copia de seguridad** en el menú principal para visualizar los servidores con el servicio de copia de seguridad de EVault. 
2. Seleccione el servidor donde residen los archivos de los que va a hacer copia de seguridad. Pulse la flecha de expansión que apunta a la derecha para visualizar el enlace WebCC.
4. Pulse **Inicio de sesión de WebCC** para iniciar el cliente WebCC en el navegador.
  **Nota**: si WebCC no se inicia, es posible que haya un problema con la conexión VPN. También puede ver un mensaje que indique que el método de envío no es seguro. Esto es normal; continúe con el envío del formulario.
  
## Configurar un trabajo de copia de seguridad de BMR

1. En el panel de navegación izquierdo, pulse **Todos los agentes** para visualizar los agentes actuales de EVault
2. Pulse **Este es un nuevo agente que me gustaría configurar**.
3. Escriba un nombre de trabajo y una descripción de trabajo para el trabajo que va a configurar o crear.
4. Para **Tipo de origen de copia de seguridad**, seleccione el tipo de sistema de archivos del que desea realizar la copia de seguridad en el menú desplegable y luego pulse **Siguiente**
5. Aparecerá el menú **Selección de tipo de trabajo**. Marque el recuadro que hay junto a **Restauración nativa** y pulse **Siguiente** para continuar.
6. Pulse **Sí** en la ventana de confirmación.
7. La pantalla muestra que el nuevo trabajo ahora está en el conjunto de copia de seguridad. Pulse **Siguiente**.
8. La pantalla muestra opciones de cifrado y opciones avanzadas de seguridad. Estas normalmente no se necesitan. Pulse **Siguiente** para continuar en la pantalla **Crear una planificación**.   
9. En la página **Crear una planificación**, pulse **Añadir** para planificar un trabajo de copia de seguridad basado en tiempo o pulse **Siguiente** para crear un trabajo manual.
  - Si elige crear un trabajo manual, continúe para ejecutar su nuevo trabajo.
  - Si elige planificar un trabajo basado en tiempo, seleccione los días y la hora del día en que desea ejecutar las copias de seguridad.
  - Seleccione el esquema de retención. [Aquí](evault-backup-faq.html#how-do-the-retention-schemes-work-) encontrará más información sobre los esquemas de retención
  - Después de haber configurado la planificación de copia de seguridad, pulse **Aceptar** para guardarla. El trabajo planificado se añade a la lista de trabajos planificados. 
10. Seleccione un almacén para el trabajo de seguridad y pulse **Guardar cambios**.


## Ejecutar un trabajo de copia de seguridad de BMR
  - Si ha planificado un trabajo de copia de seguridad basado en tiempo, no hay pasos adicionales.  El trabajo se ejecutará automáticamente según lo planificado.
  - Si ha configurado un trabajo manual (sin una planificación basada en tiempo), puede ejecutarlo seleccionando su fila en la lista de trabajos y pulsando **Ejecutar copia de seguridad**. <br/> Al igual que sucede con los trabajos basados en tiempo, puede elegir el **Esquema de retención** y las **Opciones avanzadas de copia de seguridad**. Después de completar las opciones de configuración, pulse **Iniciar copia de seguridad** para iniciar el trabajo.
