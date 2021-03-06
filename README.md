
# Betaflight v4.3.x

<img src="https://raw.githubusercontent.com/wiki/betaflight/betaflight/images/betaflight/bf_logo.png">

En este repositorio iré actualizando las mejoras de **Betaflight 4.3.x** así como las configuraciones recomendadas al actualizar a esta versión.  

Recordad que para usar esta versión de Configurador de Betaflight es necesario el **Betaflight Configurator version 10.8.0**.  
Dados los errores del configurador en sus versiones 10.8.0 se aconseja el Release Candidate 3  

Si tienes dudas de como descargarte el configurador o como actualizar el firmware visita los repositorios:   

[Actualizar firmware 4.3.x] https://github.com/AirbenderFPV/Actualizar-Firmware   

[Configurador de Betaflight v10.8.xx] https://github.com/betaflight/betaflight-configurator/releases/tag/10.8.0-RC3   

Si aún estás usando **Betaflight Configurator version 10.7.0** lo más aconsejable es desinstalar ese configurador previamente.  
Para trabajar con versiones de firmware v4.2.9 se aconseja usar **Betaflight Configurator version 10.7.0**  
Mas información sobre versiones 4.2.X: https://github.com/AirbenderFPV/Betaflight-4.2.0   

Menú Betaflight 4.3.x  
=====================================================================

Antes de detallar las diferentes pestañas de ajuste de esta versión y sus ajustes, mencionar que se ha usado la **version 4.3 - RC2** de firmware.  
Al instalar la versión de firmware y conectar la placa por primera vez aparecerá un mensaje para **Aplicar los valores por defecto**, es muy importante hacer este paso correctamente o puede ser que betaflight no reconozca todas las propiedades de tu controladora (FC).  

<img src="https://raw.githubusercontent.com/AirbenderFPV/Betaflight-4.2.0/main/images/00_Valores.PNG">  


## Pantalla de Ajustes  

En esta versión de Betaflight es **obligatorio calibrar** nuestro al menos una vez antes de volar.  

<img src="https://raw.githubusercontent.com/AirbenderFPV/Betaflight-4.2.0/main/images/01_Ajuste.PNG">  

Para **Calibrar el Acelerómetro** situar nuestro quad en una superficie plana y dar al botón de calibrar.   

## Puertos  

En esta pestaña se configuran las funciones de los UART de la controladora de vuelo.    

<img src="https://raw.githubusercontent.com/AirbenderFPV/Betaflight-4.2.0/main/images/02_Puertos.PNG"> 

Asignar el **RX Serie** al puerto (UART) donde tengáis conectado el receptor.   
Asignar el **MSP** al puerto (UART) donde tengáis conectado el DJI Caddx Vista.  
Asignar los **Periféricos** en el puerto (UART) donde tengas conectado el smartAudio del VTX analógico.   

En la imagen tendríamos conectado el receptor al puerto 1 (UART1). En algunas placas este puerto es el SBUS de la controladora.  
También tendríamos conectado el sistema Caddx Vista en el puerto 5 (UART5).   

_Bajo ningún concepto se recomienda deshabilitar el MSP del **USB VCP** ya que es la conexión con el ordenador_

## Pantalla de Configuración  

En esta pantalla podremos acceder a parametros de la configuración de la controladora.    

<img src="https://raw.githubusercontent.com/AirbenderFPV/Betaflight-4.2.0/main/images/03_Configuración.PNG">  

El **Acelerómetro** es el sensor que nos ayuda a controlar la inclinazión del quad.  
En caso de volar en **Angle Mode** o **Horizon Mode** necesitas calibrar bien este sensor en la pantalla de ajustes.  

Normalmente las controladoras de vuelo no trae equipado un Barómetro ni un Magnetómetro.  
Lo mejor en estos casos es **Desactivar** estos dos sensores.  

Las frecuencias de actualización del Giro y del PID son importantísimas para volar.  
Estas están condicionadas al tipo de controladora de vuelo tengamos.  

Recomendaciones generales:  

Frecuencia de actualización del Giro: 8K  
Frecuencia del ciclo:  
4K (Recomendable para controladoras F4)  
8K (Recomendable para controladoras F7)  

Repasar también los valores del protocolo **DSHOT** en la pestaña de motores.    

En el apartado **Otras funcionalidades** tendrían que estar el **Airmode y OSD habilitados**.  

## Pantalla de Energía y Batería

Esta pantalla nos ayuda con la gestión del voltaje y la corriente de nuestro quad.

<img src="https://raw.githubusercontent.com/AirbenderFPV/Betaflight-4.2.0/main/images/04_Energiaybateria.PNG">

Para calibrar el sensor de voltaje tendremos que usar un Multímetro para saber el voltaje real de nuestra batería.  
Posteriormente, enchufar la LiPo e incrementar/disminuir el valor de **Escala** en el medidor de voltaje hasta que el valor del medidor de voltaje concuerde con el medido con el multímetro. Normalmente, este sensor viene calibrado, por lo que no es recomendable tocar los valores de fábrica.  

Para calibrar el sensor de corriente es un proceso más tedioso y no es obligatorio para empezar a volar.   
Si queremos calibrarlo tenemos que contar con un **cargador que nos indique que cantidad de miliamperios (mah)** que carga en cada ciclo. Tendremos que anotar los mah cargados individualmente de cada LiPo. En el OSD de nuestro quad tendremos que visualizar los mah consumidos y anotarlos al finalizar cada vuelo. Con estos datos, iremos modificando el valor _Escala_ del **Medidor de Amperaje**   

_New scale = Old scale X (OSD_mah_Consumed/mah_Charged)_  

Ejemplo:

Lipo cargada: 850mah = mah charged
Valor en OSD (al finalizar vuelo): 975mah = OSD_mah_Consumed
Escala: 400 = Old Scale

Obtenemos el nuevo valor de la escala : 400*(950/850) = **447**

Y repetiríamos este proceso hasta que el valor del OSD sea el mismo que el del cargador, de esta forma tendremos un control más exhaustivo del consumo de nuestra Lipo.  
Puedes consultar los escalados recomendados por el fabricante en el manual de tu controladora de vuelo, como en los siguientes ejemplos:  

[MAMBA F405MK2] https://www.diatone.us/collections/mamba-stack/products/mamba-f405-mk%E2%85%B1-flight-controller-stack

[MAMBA F722] https://www.diatone.us/collections/mamba-stack/products/mamba-f722s-flight-controller-stack

Para mas información visita:  

[Repertorio Baterias] https://github.com/AirbenderFPV/Baterias

## PREAJUSTES

Uno de los mayores cambios en esta version de configurador, la pantalla de Preajustes o "Presets" que pueden ser de mucha ayuda para adaptar los ajustes de tu quad.   
No se aconseja hacer cambios y empezar poniendo presets si estas empezando en el hobby.

<img src="https://raw.githubusercontent.com/AirbenderFPV/Betaflight-4.2.0/main/images/05_Preajuste.PNG">  

Es aconsejable hacer una copia de seguridad antes de hacer cambios importantes, por si tenemos que deshacer estos cambios de forma rapida.  

_Nota: Publicaré los ajustes y presets y podrás encontrarlos en el configurador, de momento visita el apartado de la pantalla CLI. _   


Pantalla de Ajustar PID
=====================

#### PID  

Esta pestaña nos ayuda a calibrar el PID de nuestro quad, si tienes poca experiencia es mejor dejar los ajustes por defecto.  

<img src="https://raw.githubusercontent.com/AirbenderFPV/Betaflight-4.2.0/main/images/06_Pids.PNG">

#### TASAS  

En esta versión de Betaflight podemos usar los rates de otros configuradores.  
Si no estas seguro de como funciona marca Betaflight y pon los rates que tenias en anteriores versiones.

<img src="https://raw.githubusercontent.com/AirbenderFPV/Betaflight-4.2.0/main/images/061_Tasas.PNG">

Los rates o tasas que muestran la imagen son los que he provado en esta version.  
Si os parecen muy agresivos o quereis un vuelo mas smooth podeis bajar las Tasas RC a 1.00 y anular la Expo RC en 0.  


#### FILTROS  
Esta pestaña nos ayuda a filtrar las señales de nuestro quad, si tienes poca experiencia es mejor dejar los ajustes por defecto.  

<img src="https://raw.githubusercontent.com/AirbenderFPV/Betaflight-4.2.0/main/images/062_Filtros.PNG">   

Además, los valores multiplicadores **Filtro Giro** y **Filtro D Term** se pueden mover un poco para filtrar menos la señal que enviamos a nuestro quad y tener una respuesta mas rapida. Hay que mover los dos por igual.  

Personalmente he provado el valor **1.2 en ambos**, si provais alguno y no os convence volver a el valor por defecto 1 en ambos.  

Es muy recomendable en esta pestaña editar los valores del **Filtro Notch Dinámico** situado en la parte inferior izquierda.  
Aún por confirmar, los valores recomdendados y provados por Joshua Bradwell y UAV Tech en 4.2 eran:  
Notch Count = 4  
Giro Filtro Notch Dinámico Q =300   
Giro Filtro Notch Dinámico Min =125 
Giro Filtro Notch Dinámico Max =600

## Pantalla de Modos

En esta pestaña se configuran los modos que tendrá tu quad.  

## Pantalla de OSD

En esta pestaña se configura el OSD.  
Es importante añadir que en esta versión hay mas elementos compatibles con el sistema digital de DJI pero aún no podemos visualizar ciertos parametros como...  
Si tienes problemas para visualizar el OSD tienes que revisar la conexión entre FC y VTX/Caddx.  

## Pantalla de Transmisor de Video

Será necesario volver a cargar la tabla de nuestro VTX (Archivo.JSON) y tener configurado el Uart pertinente.  

[Repertorio VTX] https://github.com/AirbenderFPV/VTX

## MOTORES:  

<img src="https://raw.githubusercontent.com/AirbenderFPV/Betaflight-4.2.0/main/images/07_Motores.PNG">  


#### Configuración del sistema y DShot settings:  


Consulta en las especificaciones de tus ESCs o 4in1 que DSHOT tiene antes de aplicar cualquier corrección.  
Se puede habilitar el bidirectional con el switch **DShot Bidirectional**.  
También hay que consultar en las especificaciones de tus ESCs o 4in1 si lo soporta.  

Recomendaciones generales:  
dshot300 -> 4k max pidloop (Recomendable para controladoras F4)  
dshot600 -> 8k max pidloop (Recomendable para controladoras F7)   

Para la actualización de firmware de los ESC o 4in1 visita:

[Repertorio ESC and 4in1] https://github.com/AirbenderFPV

## Pantalla de Caja Negra

La caja negra nos ayuda a guardar datos de los sensores en tiempo real para su posterior analisis.  
Para un mejor rendimiento de la controladora de vuelo, si no vamos a usar la caja negra, es mejor **desactivarla**.

[Notas de la versión] https://github.com/betaflight/blackbox-log-viewer/releases

Descarga el software para ver los log de la caja negra:  
https://github.com/betaflight/blackbox-log-viewer



## CLI

La consola de comandos o CLI, es una pestaña que nos deja escribir comandos a nuestra controladora minimizando el tiempo ya que podemos ajustar nuestro quad en un momento sin necesidad de recorrer pestaña a pestaña para cambiar un parametro en cada una.  

<img src="https://raw.githubusercontent.com/AirbenderFPV/Betaflight-4.2.0/main/images/08_CLI.PNG">   

Es importantisimo hacer una copia de seguridad antes de aplicar cambios en el CLI, para prevenir.  

El comando mas usual es el _diff_ que nos mostrara todos los ajustes que tenemos diferentes a la configuración inicial de betaflight.  
Este comando es muy útil para hacer copias de seguridad, ya que podemos escribir ese comando y copiar en un .txt el resultado que nos da el CLI para tener una copia de seguridad de nuestra configuración.  

El comando que no podemos olvidar es el _Save_ después de aplicar cambios tendremos que guardar siempre nuestra configuración. No os preucupeis si betaflight desconecta la controladora por un momento y teneis que volver a conectar. De esta forma estareis seguros de que se ha guardado correctamente vuestra configuración.

Os dejo mis configuraciones por si quereis provar algunos, solo teneis que copiar y pegar en el CLI.  
Si no entiendes esta parte es mejor que no la apliques.  

RATES AIRBENDER:  

Los comandos pondrán automáticamente los rates de la imagen de la pestaña TASAS en tu drone.  

set rates_type = BETAFLIGHT  
set roll_rc_rate = 120  
set pitch_rc_rate = 120  
set yaw_rc_rate = 100  
set roll_expo = 50  
set pitch_expo = 50  
set roll_srate = 70  
set pitch_srate = 70  
set yaw_srate = 70  
save  

OSD AIRBENDER:   

Los comandos pondrán automáticamente la configuración del OSD que uso yo, el OSD es muy personalizable y es preferible que cada uno lo configure a su gusto.  

set osd_rssi_alarm = 50  
set osd_cap_alarm = 800  
set osd_alt_alarm = 120  
set osd_vbat_pos = 2102  
set osd_rssi_pos = 2168  
set osd_tim_2_pos = 0  
set osd_flymode_pos = 2382  
set osd_throttle_pos = 99  
set osd_current_pos = 2116  
set osd_mah_drawn_pos = 2084  
set osd_craft_name_pos = 392  
set osd_warnings_pos = 2345  
set osd_avg_cell_voltage_pos = 2134  
set osd_battery_usage_pos = 16  
set osd_core_temp_pos = 67  
set osd_stat_tim_2 = OFF  
set osd_stat_max_spd = OFF  
set osd_stat_bbox = OFF  
set osd_stat_bb_no = OFF  
save  

Limitar potencia de los motores según las celdas de la Lipo que usemos [https://www.youtube.com/watch?v=iUJjg3ojrbg] :  

profile 0  
set profile_name = 4S  
set auto_profile_cell_count = 4  
profile 1  
set profile_name = 5S  
set motor_output_limit = 86  
set auto_profile_cell_count = 5  
profile 2  
set profile_name = XS  
set auto_profile_cell_count = -1  

#### Fuentes de información

[Notas oficiales de la versión] https://github.com/betaflight/betaflight/wiki/4.2-Tuning-Notes  

[Joshua Bardwell] https://www.youtube.com/watch?v=LkBWRiEGKTI  

[UAV Tech] https://www.youtube.com/watch?v=znyiaN5dSxc 

[QuadMx Drones] https://www.youtube.com/watch?v=tCgN-EwdSQ8   
 
[Midronedecarreras] https://www.midronedecarreras.com/betaflight/#Descarga_el_Configurador_BLHeli_suite_32  

[Multicoptero X] http://www.multicopterox.es/configuracion-betaflight-matek-f405/#ESC_beacon_configuration  
 
[Airbender_FPV] https://www.instagram.com/airbender_fpv/


_El uso de esta información queda bajo la responsabilidad de cada usuario._  
