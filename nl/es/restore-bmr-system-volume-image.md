---

copyright:
  years: 1994, 2018
lastupdated: "2018-12-14"

---
{:new_window: target="_blank"}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:DomainName: data-hd-keyref="APPDomain"}
{:DomainName: data-hd-keyref="DomainName"}

# Restauración de una imagen de volumen del sistema BMR

Si necesita restaurar una copia de seguridad de una imagen nativa desde {{site.data.keyword.backup_full}}, puede restaurarla rápidamente desde el sistema BMR Rescue Kernel. Con BMR puede restaurar el sistema sin necesidad de disponer de un sistema operativo de arranque. Resulta útil si el sistema operativo ya no se puede utilizar o si se han sustituido las unidades del sistema.

## Inicio del sistema BMR Rescue Kernel

Puede acceder al sistema BMR Rescue Kernel a través del {{site.data.keyword.slportal}}.
1. Inicie una sesión en la [consola de {{site.data.keyword.cloud_notm}}](https://{DomainName}/catalog/){:new_window} y pulse el icono **Menú** de la parte superior izquierda. Seleccione **Infraestructura clásica**.

   También puede iniciar la sesión en [{{site.data.keyword.slportal}} ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://control.softlayer.com/){:new_window} 
2. Haga clic en **Almacenamiento** > **Copia de seguridad** para visualizar los servidores con servicio de copia de seguridad.
3. Pulse la **Flecha** que hay junto a la caja fuerte.
4. Pulse **Iniciar restauración nativa**. Esta acción inicia una transacción que dura unos pocos minutos. Después podrá acceder al servidor si sigue los pasos que se detallan a continuación. Recibirá un correo electrónico cuando el sistema finalice el proceso de arranque.


## Restauración desde BMR Rescue Kernel

1. Cuando se cargue la transacción de BMR Rescue Kernel, podrá acceder de dos formas diferentes.
  - Un cliente VNC y la dirección IP privada/pública del servidor y la contraseña que aparece en el {{site.data.keyword.slportal}}
  - La consola KVM de su tarjeta IPMI.
  Ambos métodos funcionan bien.
2. Después de iniciar una sesión en BMR Rescue Kernel por primera vez, verá la pantalla de selección de idioma. Seleccione el idioma que desee y pulse **Siguiente**.
<br/>![Figura 1 - Selección de idioma de BMR](/images/bmr1.png)<br/> Se visualiza el acuerdo de licencia para el software.
3. Si acepta los términos, marque el recuadro de selección y pulse **Siguiente** para continuar. <br/> Aparece el menú principal de restauración del sistema de {{site.data.keyword.backup_notm}}.
4. Seleccione **Restaurar mi sistema**.
<br/>![Figura 2 - Menú principal de BMR](/images/bmr2.png)
5. Aparece el asistente de restauración del sistema. Seleccione **Siguiente** para continuar.
<br/>![Figura 3 - Asistente de BMR](/images/bmr3.png)
6. Seleccione un tipo de copia de seguridad desde la que realizar la restauración. Seleccione **Software de EVault** y pulse **Siguiente** para continuar.
7. En la pantalla **ubicación de copia de seguridad**, seleccione la caja fuerte y especifique la dirección de la caja fuerte, el número de cuenta, el nombre de usuario y la contraseña. Luego pulse **Siguiente** para continuar.
<br/>![Figura 4 - Elegir ubicación de copia de seguridad](/images/bmr4.png)
8. La pantalla siguiente muestra el sistema en la lista. Asegúrese de que esté resaltado y pulse **Siguiente**.
<br/>![Figura 5 - Elegir el sistema](/images/bmr5.png)
9. En la pantalla **selección de trabajo de copia de seguridad**, seleccione el trabajo desde el que desea realizar la restauración y pulse **Siguiente**.
<br/>![Figura 6 - Elegir el punto de restauración](/images/bmr6.png)
10. En el menú **Seleccionar punto de restauración**, seleccione el punto de restauración que desee y pulse **Siguiente**.
<br/>![Figura 8 - Elegir punto de restauración](/images/bmr8.png)
11. Seleccione los volúmenes de origen y de destino. Para restaurar el origen en el destino, arrastre el volumen de origen al volumen de destino.
<br/>![Figura 9 - Seleccionar volúmenes de origen y de destino](/images/bmr9.png)
12. En el recuadro de confirmación para formatear o fusionar datos, dispone de dos opciones. Seleccione **Formatear** para realizar una restauración limpia que formatea el disco. Si desea fusionar los datos en el volumen de destino, seleccione **Fusionar**.
<br/>![Figura 10 - Elegir Fusionar](/images/bmr10.png)
13. En la pantalla principal de volumen de origen y de destino, pulse **Siguiente**.
14. En la pantalla de resumen del plan de restauración, marque el recuadro para aceptar el plan y pulse **Siguiente**.
<br/>![Figura 11 - Iniciar la restauración](/images/bmr11.png)
15. Aparece la pantalla de progreso de la restauración que muestra el progreso de la restauración a medida que se lleva a cabo.
<br/>![Figura 12 - Progreso de la restauración](/images/bmr12.png)
16. Cuando finalice, recibirá una ventana de notificación que indica que la restauración ha finalizado correctamente. Pulse **Aceptar**.
17. En la pantalla de progreso de la restauración, pulse **Siguiente**.
18. En la pantalla final, marque el recuadro correspondiente a reiniciar el sistema y seleccione **Finalizar**; el servidor cargará la imagen del volumen restaurado.
  La restauración ha finalizado. <br/>

  La primera vez que suceda verá el mensaje de cierre inesperado. Es normal con este tipo de copia de seguridad y desaparece después del primer arranque.
  {:tip}
