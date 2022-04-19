
# Betaflight v4.3.x
========================

<img src="https://raw.githubusercontent.com/wiki/betaflight/betaflight/images/betaflight/bf_logo.png">

En este repositorio iré actualizando las mejoras de **Betaflight 4.3.x** así como las configuraciones recomendadas al actualizar a esta version.   
El uso de esta información queda bajo la responsabilidad de cada usuario.  
Recordad que para usar esta versión de Configurador de Betaflight es necesario el **Betaflight Configurator version 10.8.0**.  

Dados los errores del configurador en sus versiones 10.8.0 se aconseja el Release Candidate 3 
https://github.com/betaflight/betaflight-configurator/releases/tag/10.8.0-RC3 

Si tienes dudas de como descargarte el configurador o como alcualizar el firmware visita los repositorios:  

[Actualizar firmware 4.3.x]   
https://github.com/AirbenderFPV/Actualizar-Firmware  

[Actualizar/Instalar el Configurador de Betaflight v10.8.xx]  
https://github.com/betaflight/betaflight-configurator/releases   

Si aún estas usando **Betaflight Configurator version 10.7.0** lo mas aconsejable es desinstalar ese configurador previamente.  
Para trabajar con versiones de firmware v4.2.9 se aconseja usar **Betaflight Configurator version 10.7.0**  
Mas información sobre versiones 4.2.X: https://github.com/AirbenderFPV/Betaflight-4.2.0  

Menú Betaflight 4.3.x  
=====================================================================

Antes de detallar las diferentes pestañas de ajuste de esta versión y sus ajustes, mencionar que se ha usado la **version 4.3 - RC2** de firmware.  
Al instalar la versión de firmware y conectar la placa por primera vez aparecera un mensaje para **Aplicar los valores por defecto**, es muy importante hacer este paso correctamente o puede ser que betaflight no reconozca todas las propiedades de tu controladora (FC).  


### Pantalla de Ajustes  

En esta versión de Betaflight es **obligatorio calibrar** nuestro almenos una vez antes de volar.  

<img src="https://raw.githubusercontent.com/AirbenderFPV/Betaflight-4.2.0/main/images/01_Ajuste.PNG">  

Para **Calibrar el Acelerómetro** situar nuestro quad en una superficie plana y dar al botón de calibrar.   
Es aconsejable hacer una copia de seguridad antes de hacer cambios importantes, por si tenemos que deshacer estos cambios de forma rapida.

### Pantalla de Configuración  

<img src="https://raw.githubusercontent.com/AirbenderFPV/Betaflight-4.2.0/main/images/03_Configuración.PNG">  

### Pantalla de Energía y Batería

Esta pantalla nos ayuda con la gestión de el voltage y la corriente de nuestro quad. 

<img src="https://raw.githubusercontent.com/AirbenderFPV/Betaflight-4.2.0/main/images/04_Energiaybateria.PNG">

Para calibrar el sensor de voltaje tendremos que usar un Multimetro para saber el voltaje real de nuestra bateria.   
Posteriormente enchufar la LiPo y incrementar/disminuir el valor de **Escala** en el medidor de voltaje hasta que el valor del medidor de voltaje concuerde con el medido con el multimetro. 

Para calibrar el sensor de corriente podemos usar el **ADC Integrado** y ajustar el escalado tal como marca el fabricante o podemos usar la opción **Sensor ESC** si previamente lo hemos configurado en los puertos.

Puedes consutar los escalados recomendados por el fabricante en el manual de tu controladora de vuelo, como en los siguientes ejemplos:  

[MAMBA F405MK2] https://www.diatone.us/collections/mamba-stack/products/mamba-f405-mk%E2%85%B1-flight-controller-stack

[MAMBA F722] https://www.diatone.us/collections/mamba-stack/products/mamba-f722s-flight-controller-stack

Para mas información visita:  

[Repertorio Baterias] https://github.com/AirbenderFPV/Baterias


Pantalla de Ajustar PID
=====================

#### PID  

Esta pestaña nos ayuda a calibrar el PID de nuestro quad, si tienes poca experiencia es mejor dejar los ajustes por defecto.  

[PIDs] https://github.com/AirbenderFPV/PID-Betaflight-4.2/edit/main/README.md

#### TASAS  

En esta versión de Betaflight podemos usar los rates de otros configuradores.  
Si no estas seguro de como funciona marca Betaflight y pon los rates que tenias en anteriores versiones.

#### FILTROS  
Esta pestaña nos ayuda a filtrar las señales de nuestro quad, si tienes poca experiencia es mejor dejar los ajustes por defecto.  

<img src="https://raw.githubusercontent.com/AirbenderFPV/Betaflight-4.2.0/main/images/062_Filtros.PNG">

Es muy recomendable en esta pestaña editar los valores del **Filtro Notch Dinámico** situado en la parte inferior izquierda.  
Los valores recomdendados y provados por Joshua Bradwell son los que aparecen en la imagen.  
Giro Filtro Notch Dinámico Ancho = 0  
Giro Filtro Notch Dinámico Q =250   
Giro Filtro Notch Dinámico Min =90  
Giro Filtro Notch Dinámico Max =350   

Además, los valores multiplicadores **Filtro Giro** y **Filtro D Term** se pueden mover un poco para filtrar menos la señal que enviamos a nuestro quad y tener una respuesta mas rapida. Hay que mover los dos por igual.  

Personalmente he provado el valor **1.2 en ambos**, si provais alguno y no os convence volver a el valor por defecto 1 en ambos.  

Para mas información de ajustes rapidos recomendados visita:

[Ajustes rapidos recomendados en Betaflight 4.2.x] https://github.com/AirbenderFPV/Ajustes-rapidos-recomendados-en-Betaflight-4.2.x


### Pantalla de Modos

Será necesario volver a configurar esta pantalla.

### Pantalla de OSD

Será necesario volver a configurar esta pantalla.

### Pantalla de Transmisor de Video

Será necesario volver a cargar la tabla de nuestro VTX (Archivo.JSON) y tener configurado el Uart pertinente.  

[Repertorio VTX] https://github.com/AirbenderFPV/VTX

#### MOTORES:  

<img src="https://raw.githubusercontent.com/AirbenderFPV/Betaflight-4.2.0/main/images/07_Motores.PNG">  

Por defecto el numero de **Polos del motor** viene como 14. Estos son el numero de imanes que tiene tu campana de motor.  
En tinnys a veces este numero se reduce ya que los motores son mas pequeños. Rondan sobre 12.  
Lo mejor es asegurarse mirando una campana de nuestros motores.  


#### Configuración del sistema y DShot settings:  

El **Acelerómetro** es el sensor que nos ayuda a controlar la inclinazión del quad.    
En caso de volar en **Angle Mode** o **Horizon Mode** necesitas tener activado este sensor.  
Revisa la pantalla de Ajustes para ver como calibrar el quad si usas esos modos.  
Normalmente las controladoras de vuelo no trae equipado un Barómetro ni un Magnetómetro.   
Lo mejor en estos casos es **Desactivar** estos dos sensores.  

Las frequencias del sersor Giro y del PID son importantisimas para volar.  
Estas estan condicionadas a el tipo de controladora de vuelo tengamos, una F7 irá mejor que una F4.  
Si tienes poca experiencia es mejor dejar los ajustes por defecto.  
Consulta en las especificaciones de tus ESCs o 4in1 que DSHOT tiene antes de aplicar cualquier corrección.  
Se puede habilitar el bidirectional con el switch **DShot Bidirectional**.  
También hay que consultar en las especificaciones de tus ESCs o 4in1 si lo soporta.  

- Con el filtro rpm habilitado   
dshot300 -> 4k max pidloop (Recomendable para controladoras F4)  
dshot600 -> 8k max pidloop (Recomendable para controladoras F7)   

- Usando el bidirectional y con el filtro rpm habilitados:     

dshot150 -> 2k max pidloop   
dshot300 -> 4k max pidloop (Recomendable para controladoras F4)     
dshot600 -> 8k max pidloop (Recomendable para controladoras F7)    

- Sin usar el bidirectional y con el filtro rpm habilitados:    

dshot150 -> 4k max pidloop (Recomendable para controladoras F4)   
dshot300 -> 8k max pidlopp (Recomendable para controladoras F7)  
dshot600 -> up to 16k max pidloop (8k es el maximo que se puede configurar en la versión 4.2)  

Para la actualización de firmware de los ESC o 4in1 visita:

[Repertorio ESC and 4in1] https://github.com/AirbenderFPV

### Pantalla de Caja Negra

La caja negra nos ayuda a guardar datos de los sensores en tiempo real para su posterior analisis.  
Para un mejor rendimiento de la controladora de vuelo, si no vamos a usar la caja negra, es mejor **desactivarla**.

[Notas de la versión] https://github.com/betaflight/blackbox-log-viewer/releases

Descarga el software para ver los log de la caja negra:  
https://github.com/betaflight/blackbox-log-viewer


### CLI


<img src="https://raw.githubusercontent.com/AirbenderFPV/Betaflight-4.2.0/main/images/08_CLI.PNG">  






#### Fuentes de información

[Notas oficiales de la versión] https://github.com/betaflight/betaflight/wiki/4.2-Tuning-Notes  

[Joshua Bardwell] https://www.youtube.com/watch?v=CCbaHjF-ZL0

[QuadMx Drones] https://www.youtube.com/watch?v=tCgN-EwdSQ8   
 
[Midronedecarreras] https://www.midronedecarreras.com/betaflight/#Descarga_el_Configurador_BLHeli_suite_32  

[Multicoptero X] http://www.multicopterox.es/configuracion-betaflight-matek-f405/#ESC_beacon_configuration

[Airbender_FPV] https://www.instagram.com/airbender_fpv/
