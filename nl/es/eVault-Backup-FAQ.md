---

copyright:
  years: 1994, 2018
lastupdated: "2018-07-10"

---
{:new_window: target="_blank"}


# Copia de seguridad de EVault: preguntas más frecuentes

**¿De qué tipo de aplicaciones se puede hacer copia de seguridad con EVault?**

Se puede utilizar EVault para realizar una copia de seguridad de varias aplicaciones. Sin embargo, {{site.data.keyword.BluSoftlayer_full}} ofrece agentes de software para algunos de los sistemas de software más comunes de los que se hace copia de seguridad, que incluyen:

- Restauración nativa
- Microsoft SQL
- Oracle

Los plugins que se muestran aquí solo son compatibles con servidores Windows. Cada agente está disponible como un complemento del servicio de copia de seguridad EVault. Para añadir un agente al servicio, póngase en contacto hoy mismo con el equipo de ventas. 

<hr>

**¿Con qué frecuencia se puede hacer copia de seguridad de los datos con EVault?**

Puede hacer copia de seguridad de sus datos con la frecuencia que desee. En WebCC, las copias de seguridad se pueden realizar manualmente o se pueden planificar para que se ejecuten una vez o como un proceso repetitivo. Las copias de seguridad repetitivas pueden ser diarias, semanales, mensuales o según una planificación personalizada y se pueden actualizar o cancelar en cualquier momento.

>**Nota**: las copias de seguridad muy frecuentes que se ejecutan varias veces al día o cada hora podrían hacer que los trabajos de copia de seguridad resultaran dañados. Esto se debe a que es posible que el almacén no pueda eliminar los conjuntos seguros antiguos o realizar otras tareas de fondo necesarias entre ejecuciones.

<hr>

**¿Cómo funcionan los esquemas de retención?**

EVault permite la retención de datos en función del tiempo al que desee retrotraer. Los esquemas de retención **diarios** conservan los datos durante siete días, mientras que los esquemas **semanales** conservan los datos durante un mes y los esquemas **mensuales** los conservan durante un año. Al final de cada periodo, el conjunto de datos más antiguo queda apartado y la primera "copia de seguridad delta" realizada se convierte en el punto de restauración más antiguo disponible. 

<hr>

**¿Qué es la tecnología delta?**

La primera copia de seguridad es un “inicio” (una copia de seguridad completa) y las siguientes son "deltas" (es decir, solo cambios), pero son equivalentes y se siguen considerando "copias de seguridad completas". Es decir, puede restaurar a partir de las mismas todos los archivos o archivos seleccionados. Esta tecnología permite realizar "copias de seguridad completas" en cada sesión, pero ahorra una enorme cantidad de espacio en el almacén y reduce el tiempo necesario para realizar cada una de las siguientes copias de seguridad.

<hr>

**¿Son seguras las copias de seguridad?**

De forma predeterminada, todo el cifrado sobre cable (OTW) se cifra con el tipo de cifrado AES de 256 bits. También puede optar por almacenar los datos en formato cifrado utilizando AES de 256 bits. 

>**Nota**: debe recordar su contraseña de cifrado. Los datos no se pueden restaurar sin esta contraseña. Si pierde la contraseña, no podrá recuperar sus datos. 

Las proporciones de compresión permiten entre compresión cero y proporciones máximas de compresión que, en función del tipo de archivo, pueden ser de entre el 20 por ciento y el 30 por ciento.

<hr>

**¿Qué información se guarda con las copias de seguridad de estado del sistema?**

Las copias de seguridad de estado del sistema incluyen, aunque sin limitarse a los mismos, COM + base de datos de registro de clase, registro, archivos de arranque, archivos del sistema y recuento de rendimiento. Todos dependen del sistema. Los archivos del sistema varían según el SO del sistema y los paquetes de servicio. Normalmente hay varios miles de ellos. MS Windows crea una lista dinámica de estos DLL cuando el usuario los incluye en la copia de seguridad. Si incluye los archivos del sistema, puede recuperar archivos del sistema dañados, o realizar una recuperación si desinstala accidentalmente algunos paquetes de servicio o si desea realizar una recuperación con una restauración desde cero. Puede volver al estado de la copia de seguridad sin tener que volver a instalar el sistema operativo desde el kit de instalación y luego instalar cada paquete de servicio por separado.

>**Nota**: no se incluye ningún archivo de datos en una copia de seguridad de estado del sistema. Un trabajo de copia de seguridad de estado del sistema se debe configurar como un trabajo autónomo. No debe haber ningún otro origen de datos que esté incluido en el trabajo de copia de seguridad de estado del sistema.

<hr>

**¿Qué sucede con los archivos abiertos?**

De forma predeterminada, el cliente base dispone de la tecnología más innovadora para manejar la mayoría de los archivos abiertos que se ejecutan en el sistema operativo.

<hr>

**¿Dónde puedo encontrar información sobre los precios?**

Para obtener más información, consulte [Almacenamiento de copia de seguridad](https://www.ibm.com/cloud/backup-and-restore){:new_window} y [EVault en IBM Cloud: precios](https://www.ibm.com/cloud/evault/pricing){:new_window}.

<hr>

**¿Puedo aumentar o reducir mi capacidad de EVault sin poner en riesgo mis copias de seguridad?**

Puede aumentar o reducir el tamaño de su EVault a través del [ {{site.data.keyword.slportal}} ](https://control.softlayer.com/){:new_window}. La modificación de la capacidad de EVault no afecta a la integridad de los datos que se guardan en el almacén. Para obtener más información, consulte [Ampliación de la capacidad de EVault](expanding-evault-capacity.html).

<hr>

**¿Qué sucede su supero mi capacidad de EVault?**

Todavía puede guardar y recuperar sus copias de seguridad, aunque alcance el límite de la capacidad que ha adquirido anteriormente. Tenga en cuenta que se aplicará un cargo por cada GB adicional que utilice.
