---

copyright:
  years: 1994, 2017
lastupdated: "2017-10-04"

---
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}

# Terminología de la copia de seguridad y la restauración de EVault 

## Tecnología Delta:
La primera copia de seguridad es un “inicio” (una copia de seguridad completa) y las siguientes son deltas (es decir, solo cambios), pero son equivalentes y se siguen considerando copias de seguridad “completas”. Es decir, puede restaurar a partir de las mismas todos los archivos o archivos seleccionados. Esta tecnología permite realizar “copias de seguridad completas” en cada sesión, pero ahorra una enorme cantidad de espacio en el almacén y reduce el tiempo necesario para realizar cada una de las siguientes copias de seguridad.

## Esquemas de retención: 
EVault permite la retención de datos en función del tiempo al que desee retrotraer. Los esquemas de retención diaria conservan los datos durante 7 días, mientras que los semanales conservan los datos durante 1 mes y los mensuales durante 1 año. Al final de cada período, el conjunto de datos más antiguo queda apartado y el primer delta realizado se convierte en punto de restauración más antiguo disponible. 

## Compresión: 
EVault ofrece 6 tipos de soluciones de cifrado para sus datos: DES 56bit, Blowfish 56 bit, Triple DES 112bit, Blowfish 128 bit, AES 128 bit y AES 256 bit. Las proporciones de compresión permiten entre compresión cero y proporciones máximas de compresión que, en función de cada tipo de archivos, pueden ser de entre 20 % y 30 %.

## Cifrado:
De forma predeterminada, todo el cifrado sobre cable (OTW) se cifra con el tipo de cifrado AES 128bit. Si desea que los datos se guarden en un formato cifrado, dispone de varias opciones como parte del proceso de copia de seguridad. Tenga en cuenta que, si pierde la contraseña, NO podrá recuperar sus datos. 

## Copias de seguridad especiales: 
Las copias de seguridad de estado del sistema incluyen, aunque sin limitarse a los mismos, COM + base de datos de registro de clase, registro, archivos de arranque, archivos del sistema, recuento de rendimiento, todos ellos en función del sistema. Los archivos del sistema varían según el SO del sistema y los paquetes de servicio. Normalmente hay varios miles de ellos. MS Windows crea una lista dinámica de estos DLL cuando el usuario los incluye en la copia de seguridad. La inclusión de los archivos del sistema le permite recuperar archivos del sistema dañados, o realizar una recuperación si desinstala accidentalmente algunos paquetes de servicio o si desea realizar una recuperación con una restauración desde cero. Esto le permite volver al estado de la copia de seguridad sin tener que tener que volver a instalar el sistema operativo desde el kit de instalación y luego instalar cada paquete de servicio por separado. 

## Archivos abiertos: 
De forma predeterminada, el cliente base dispone de la tecnología más innovadora para manejar la mayoría de los archivos que se ejecutan en el sistema operativo. En el caso poco probable de que las copias de seguridad fallen debido a una limitación de archivos abiertos, hay plugins secundarios que puede adquirir para mejorar el manejo de los archivos abiertos. La regla general es que no necesita el plugin de archivos abiertos a menos que observe errores en sus copias de seguridad para archivos abiertos; en este caso puede solicitar los plugins.
