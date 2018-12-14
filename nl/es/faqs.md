---

copyright:
  years: 1994, 2018
lastupdated: "2018-12-14"

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:faq: data-hd-content-type='faq'}


# Preguntas más frecuentes

## ¿De qué tipo de aplicaciones se puede hacer copia de seguridad?
{: faq}

Se puede utilizar {{site.data.keyword.backup_full}} para realizar una copia de seguridad de varias aplicaciones. Sin embargo, {{site.data.keyword.BluSoftlayer_full}} ofrece agentes de software para algunos de los sistemas de software más comunes de los que se hace copia de seguridad, que incluyen:

- Restauración nativa
- Microsoft Exchange
- Microsoft SQL
- Oracle

Los plugins que se muestran aquí solo son compatibles con servidores Windows, con la excepción del plugin Oracle. Cada agente está disponible como un complemento del servicio de copia de seguridad. Para añadir un agente al servicio, póngase en contacto hoy mismo con el equipo de ventas.

<hr>

## ¿Con qué frecuencia se puede realizar una copia de seguridad de los datos?
{: faq}

Dentro de WebCC, las copias de seguridad se pueden realizar manualmente, o se pueden planificar como una sola instancia, o para ser recurrentes. Las copias de seguridad repetitivas pueden ser diarias, semanales, mensuales o según una planificación personalizada y se pueden actualizar o cancelar en cualquier momento.

Las copias de seguridad muy frecuentes que se ejecutan varias veces al día o cada hora podrían hacer que los trabajos de copia de seguridad resultaran dañados. Esta corrupción se produce porque el almacenamiento de copia de seguridad no tiene suficiente tiempo para ejecutar las tareas de mantenimiento en segundo plano necesarias. Los trabajos de copia de seguridad tienen prioridad sobre las tareas de mantenimiento. Por lo tanto, en caso de copias de seguridad muy frecuentes, la caja fuerte sigue ejecutando los trabajos de copia de seguridad y hace que el número de conjuntos de seguridad aumente.
{:note}

<hr>

## ¿Cómo funcionan los esquemas de retención?
{: faq}

{{site.data.keyword.backup_notm}} permite la retención de datos en función del tiempo al que desee retrotraer. Los esquemas de retención **diarios** conservan los datos durante siete días, mientras que los esquemas **semanales** conservan los datos durante un mes y los esquemas **mensuales** los conservan durante un año. Al final de cada periodo, el conjunto de datos más antiguo queda apartado y la primera "copia de seguridad delta" realizada se convierte en el punto de restauración más antiguo disponible.

Puede modificar los esquemas de retención predeterminados y puede crear esquemas de retención personalizados. Sin embargo, es muy recomendable utilizar las retenciones predeterminadas como punto de partida. Cuando se crea un nuevo esquema de retención o se modifica una retención existente, asegúrese de que la opción Archivado no esté seleccionada. El archivado no está soportado.
{:tip}

<hr>

## ¿Qué es la tecnología delta?
{: faq}

La primera copia de seguridad es un “inicio” (una copia de seguridad completa) y las siguientes son "deltas" (es decir, solo cambios), pero son equivalentes y se siguen considerando "copias de seguridad completas". Es decir, puede restaurar a partir de las mismas todos los archivos o archivos seleccionados. Esta tecnología permite realizar "copias de seguridad completas" en cada sesión, pero ahorra una enorme cantidad de espacio en la caja fuerte y reduce el tiempo necesario para realizar cada una de las siguientes copias de seguridad.

<hr>

## ¿Son seguras las copias de seguridad?
{: faq}

De forma predeterminada, todo el cifrado sobre cable (OTW) se cifra con el tipo de cifrado AES de 256 bits. También puede optar por almacenar los datos en formato cifrado utilizando AES de 256 bits.

Debe recordar la contraseña de cifrado. Los datos no se pueden restaurar sin esta contraseña. Si pierde la contraseña, no podrá recuperar sus datos.
{:important}

Las proporciones de compresión permiten entre compresión cero y proporciones máximas de compresión que, en función del tipo de archivo, pueden ser de entre el 20 por ciento y el 30 por ciento.

<hr>

## ¿Qué información se guarda con las copias de seguridad de estado del sistema?
{: faq}

Las copias de seguridad de estado del sistema incluyen, aunque sin limitarse a los mismos, COM + base de datos de registro de clase, registro, archivos de arranque, archivos del sistema y recuento de rendimiento. Todos dependen del sistema. Los archivos del sistema varían según el SO del sistema y los paquetes de servicio. Normalmente hay varios miles de ellos. MS Windows crea una lista dinámica de estos DLL cuando el usuario los incluye en la copia de seguridad. Si incluye los archivos del sistema, puede recuperar archivos del sistema dañados, o realizar una recuperación si desinstala accidentalmente algunos paquetes de servicio o si desea realizar una recuperación con una restauración desde cero. Puede volver al estado de la copia de seguridad sin tener que volver a instalar el sistema operativo desde el kit de instalación y luego instalar cada paquete de servicio por separado.

No se incluye ningún archivo de datos de usuario en la copia de seguridad del estado del sistema. Un trabajo de copia de seguridad de estado del sistema se debe configurar como un trabajo autónomo. No debe haber ningún otro origen de datos que esté incluido en el trabajo de copia de seguridad del estado del sistema
{:important}

<hr>

## ¿Qué sucede con los archivos abiertos?
{: faq}

De forma predeterminada, el cliente base dispone de la tecnología más innovadora para manejar la mayoría de los archivos abiertos que se ejecutan en el sistema operativo.

<hr>

## ¿Dónde puedo encontrar información sobre los precios?
{: faq}

Para obtener más información, consulte [Almacenamiento de copia de seguridad](https://www.ibm.com/cloud/backup-and-restore){:new_window} y [{{site.data.keyword.backup_notm}} en IBM Cloud: precios](https://www.ibm.com/cloud/evault/pricing){:new_window}.

<hr>

## ¿Se puede aumentar o reducir la capacidad de {{site.data.keyword.backup_notm}} sin poner en riesgo las copias de seguridad?
{: faq}

Puede aumentar o reducir el tamaño de su caja fuerte a través del [ {{site.data.keyword.slportal}} ](https://control.softlayer.com/){:new_window}. La modificación de la capacidad no afecta a la integridad de los datos que se almacenan en la caja fuerte. Para obtener más información, consulte [Ampliación de la capacidad](expanding-capacity.html).

<hr>

## ¿Qué sucede cuando se supera la capacidad de {{site.data.keyword.backup_notm}}?
{: faq}

Todavía puede guardar y recuperar sus copias de seguridad, aunque alcance el límite de la capacidad que ha adquirido anteriormente. Sin embargo, tenga en cuenta que en la factura habrá un cargo adicional para cada GB adicional utilizado.

<hr>

## ¿Cómo puedo configurar notificaciones en WebCC para que me avise si fallan las copias de seguridad?
{: faq}

Las notificaciones se pueden configurar en el separador Avanzado. Siga las instrucciones que encontrará en **Enlaces rápidos** en WebCC.
