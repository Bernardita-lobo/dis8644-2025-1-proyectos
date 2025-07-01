# proyecto-02

## Acerca del proyecto

- Grupo: 06

- Integrantes:
  - Santiago Gaete Fernández @07-clifford1one
  - Anaís Marschhausen Gajardo @10-Anaisbmg
  - Sebastián Sáez Olivares @19-SebastianSaez1003

- Chips usados:
  - NE555
  - L293D

## Presentación textual

El fps555 es un dispositivo de protección ocular con posición adaptable mecánicamente. consiste en un circuito que recibe un input a través de un interruptor ON-OFF-ON. Esta acción provoca un output de rotación mecánico, ajustando la posición de los lentes..

## Dibujos de diagramas del circuito (1 punto)

Este es el diagrama a mano, desde la perspectiva de un usuario interactuando con nuestro proyecto.

![Dibujo del diagrama a mano](./imagenes/diagramaFlujo-dibujo.jpg)

## Prototipado de circuitos en protoboard (1 punto)

En un principio queríamos que nuestro circuito funcionara gracias a un servomotor para crear un movimiento controlado al interactuar con nuestro producto, pero no funcionó ningún circuito que encontramos en internet, y los que sí funcionaban requieren Arduino para su funcionamiento.

A continuación, un video de todos los componentes y la protoboard que habíamos armado:

[![video que envió Santi](https://img.youtube.com/vi/8piNzuUTGBI/maxresdefault.jpg)](https://youtube.com/shorts/8piNzuUTGBI)

Luego Matías nos explicó sobre los puentes H, donde podíamos controlar la velocidad y la dirección del movimiento de un motor como el que se encontraba en nuestro kit.

También se nos mencionó que existe un chip integrado que realizaba esta función, pero de igual manera se hizo una prueba del circuito de manera mecánica, con 4 botones, a que era lo que más se asemejaba al esquemático del puente H a primera vista.

**El funcionamiento era el siguiente:**

Se armaron 2 circuitos PWM donde su output eran conectados hacia botones, donde el circuito 1 quedaría posicionado con su output al positivo del motor, mientras que a través de otro botón se dejaría pasar la conexión para completar el circuito, mientras que el circuito 2 estaría de la manera opuesta, todo esto para que no ocurriese ningún cortocircuito.

![puente H con botones y leds prendidos](./imagenes/puenteHbotones-1.jpg)

![puente H con botones y leds apagados para mejor visualizacion](./imagenes/puenteHbotones-2.jpg)

![puente H con botones y detector de umbral, version que no fue usada al final](./imagenes/puenteHbotones-3.jpg)

Video de prueba del puente H con 4 botones, hecho de manera mecánica:

[![Video de prueba del puente H con 4 botones, hecho de manera mecánica](https://img.youtube.com/vi/82sJYsFwlOw/maxresdefault.jpg)](https://youtube.com/shorts/82sJYsFwlOw)

Luego pasamos a integrar el chip L293D con el que se pudo reducir su funcionamiento a simplemente 2 botones, uno para cada dirección del motor.

![L293D con botones](./imagenes/l293dBotones-2.jpg)

Video de prueba del chip al tener 2 botones:

[![Video de prueba del chip al solo tener 2 botones](https://img.youtube.com/vi/P7w4akQcq58/maxresdefault.jpg)](https://youtube.com/shorts/P7w4akQcq58)

Luego se integró el switch 6 PDT para poder generar este cambio de dirección con tan solo 1 componente, como también el estado neutro “OFF” del motor.

![L293D on/off/on](./imagenes/l293dSwitch-1.jpg)

Pero se nos dejó claro en la clase del martes 17 de junio unas ciertas correcciones, para poder asegurarnos de que el L293D estaba correctamente conectado, como también el uso de la otra mitad de nuestro switch ON/OFF/ON, y que de esta manera no se fuese a ocupar todo el circuito de manera constante al conectarlo al pin 4 del chip 555.

Como último componente, se conectó el motor reductor de 3 rpm que compramos, para poder demostrar el funcionamiento como lo asignamos.

![foto del lateral de protoboard](./imagenes/tme-grupo06-registro01.jpg)

![foto del frontal de protoboard](./imagenes/tme-grupo06-registro02.jpg)

![foto del superior de protoboard](./imagenes/tme-grupo06-registro03.jpg)

![foto del motoreductor](./imagenes/tme-grupo06-registro04.jpg)

Video del funcionamiento de la protoboard final:

[![Funcionamiento de la protoboard final](https://img.youtube.com/vi/9qnviXXqF60/maxresdefault.jpg)](https://youtube.com/shorts/9qnviXXqF60)

Como resumen:

El circuito de entrada usa la posición del switch para determinar el estado del motoreductor.

El circuito de salida usa el L293D para cambiar el sentido de la rotación del motoreductor.

## Bill of Materials (1 punto)

bom extraído desde [repo de duckusu](https://github.com/Anaisbmg/dis8644-2025-1-proyectos/tree/main/21-duckusu/sesion-15b)

| Grupo 6  |                          |          Integrantes           |                    |                                                  |                                                             |
|:-------: |------------------------- |:-----------------------------: |------------------- |------------------------------------------------- |------------------------------------------------------------ |
|          | Santiago (clifford1one)  | Sebastián (SebastianSaez1003)  |  Anaís (Anaisbmg)  |                                                  |                                                             |
|          |                          |                                |                    |                                                  |                                                             |
|          |                          |                                |                    |                                                  |                                                             |
|   Item   |           Qty            |           Referencia           |       Valor        |                   Tipo de ítem                   |                        Accesibilidad                        |
|    1     |            2             |             R1, R2             |         1K         |                   Resistencia                    |                  Se puede conseguir en lab                  |
|    2     |            2             |             R3, R4             |        100K        |                   Resistencia                    |                  Se puede conseguir en lab                  |
|    3     |            2             |             R5, R6             |        470K        |                   Resistencia                    |                  Se puede conseguir en lab                  |
|    4     |            1             |               R7               |        10KΩ        |                   Resistencia                    |                  Se puede conseguir en lab                  |
|    5     |            6             |             D1~D6              |       1n4007       |                      Diodo                       |                   Se tendrán que comprar                    |
|    6     |            1             |               C1               |        100n         |              Condensador (cerámico)              |                  Se puede conseguir en lab                  |
|    7     |            1             |               C2               |        474         |              Condensador (cerámico)              |        Se puede conseguir en lab pero no hay muchos         |
|    8     |            1             |               D7               |        3mm         |                       Led                        |                  Se puede conseguir en lab                  |
|    9     |            1             |               U1               |        555         |                       Chip                       |                  Se puede conseguir en lab                  |
|    10    |            1             |               U2               |       L293D        |                       Chip                       |                   Se tendrán que comprar                    |
|    11    |            1             |              SW1               | 6 Pines ON-OFF-ON  |                Interruptor Switch                |                    Comprado (katode.cl)                     |
|    12    |            1             |                                |      6V 3RPM       |                 Motorreductor DC                 |                     Comprado (Afel.cl)                      |
|    13    |            1             |              RVC1              |        500K        |                  Potenciometro                   |                  Se puede conseguir en lab                  |
|    14    |            2             |                                |      2 pines       |                      Tblock                      | Se tendrán que comprar si es que no usan los que ya tienen  |
|    15    |            1             |               U1               |      8 pines       |                      Socket                      |                  Se puede conseguir en lab                  |
|    16    |            1             |               U2               |      16 pines      |                      Socket                      |                   Se tendrán que comprar                    |
|    17    |            5             |                                |                    |                    Pin Header                    |                  Se puede conseguir en lab                  |
|    18    |            5             |                                |                    | Cable dupont: terminal receptora a terminal pin  |                  Se puede conseguir en lab                  |

Compramos 3 interruptores switch de 6 Pines ON-OFF-ON y también 1 motorreductor DC de 6V 3RPM, para más info issue 05.

## Ayudas y comunicación con colegas (1 punto)

### protoboards

[issue protoboards](https://github.com/orgs/disenoUDP/projects/4/views/1?pane=issue&itemId=115280226&issue=disenoUDP%7Cdis8644-2025-1-proyectos%7C140)

- [issue 01](https://github.com/disenoUDP/dis8644-2025-1-proyectos/issues/140#issuecomment-2985358277)  
  - emisor: SebastianSaez1003  
  - enviado a: docentes
  - temática: documentación de proto en el proceso  
  - conclusión: era necesario documentar todo el progreso para entender el proceso de aprendizaje  

- [issue 02](https://github.com/disenoUDP/dis8644-2025-1-proyectos/issues/140#issuecomment-2986736213)  
  - emisor: SebastianSaez1003
  - enviado a: IzhakVillegas del grupo 00c y docentes
  - temática: feedback de formato
  - conclusión: no hemos recibido respuesta

- [issue 03](https://github.com/disenoUDP/dis8644-2025-1-proyectos/issues/148#issuecomment-2981757431)
  - emisor: SebastianSaez1003  
  - enviado a: bumwox del grupo 02
  - temática: asistencia en armado del prototipo en protoboard
  - conclusión: se ordenó y comprendió de mejor manera cómo pasar del esquemático a la protoboard para que se llegase a un resultado funcional.

- Ayuda presencial Jueves 19 de Junio 2025
  - emisor: SebastianSaez1003  
  - enviado a: bumwox del grupo 02
  - temática: integración del piezoeléctrico, jack para audífonos y conexiones finales.
  - conclusión: se integraron los componentes finales del proyecto, logrando identificar en qué lugares existían problemas de conexiones entre componentes, fijándolos en la protoboard y consiguiendo un funcionamiento constante y replicable.  

### bom

[issue bom](https://github.com/orgs/disenoUDP/projects/4/views/1?pane=issue&itemId=115280715&issue=disenoUDP%7Cdis8644-2025-1-proyectos%7C146)

- [issue 04](https://github.com/disenoUDP/dis8644-2025-1-proyectos/issues/146#issuecomment-2982287337)  
  - emisor: anaisbmg  
  - enviado a: franudp del grupo 0c y docentes
  - temática:  recomendación para conectar switch 6 pines
  - conclusión: existen nudos para cables y que podriamos utlizar resina uv o silicona para cubrir las conexiones y sí utilizábamos tblock deberíamos ocupar terminales para aislar

- [issue 05](https://github.com/disenoUDP/dis8644-2025-1-proyectos/issues/146#issuecomment-2986084119)  
  - emisor: anaisbmg
  - enviado a: duckusu del grupo 0c y docentes
  - temática: pin header y bom
  - conclusión: se confirmo nuestra idea de comprar una regleta y utilizar 5 pin, tambien existen de estos pin header en el lab
  
### esquematico

[issue esquemático](https://github.com/orgs/disenoUDP/projects/4/views/1?pane=issue&itemId=115278736&issue=disenoUDP%7Cdis8644-2025-1-proyectos%7C128)

- [issue 06](https://github.com/disenoUDP/dis8644-2025-1-proyectos/issues/128#issuecomment-2978671139)  
  - emisor: SebastianSaez1003
  - enviado a: franudp del grupo 0c y docentes
  - temática: interacción previa
  - conclusión: es más rápido etiquetar a @disenoUDP/docentes que estar etiquetando uno a uno y nos ayudaron con correcciones para nuestro esquemático

- [issue 07](https://github.com/disenoUDP/dis8644-2025-1-proyectos/issues/128#issuecomment-2981096977)  
  - emisor: clifford1one
  - enviado a: franudp del grupo 0c y docentes
  - temática: feedback símbolo para el mts303 de 6 pines
  - conclusión: existe una guía para KiCAD llamada sparkfun y se nos guío con el componente y este como estaba en la footprint

- [issue 08](https://github.com/disenoUDP/dis8644-2025-1-proyectos/issues/128#issuecomment-2989092959)  
  - emisor: clifford1one
  - enviado a: franudp del grupo 0c y docentes
  - temática: feedback respecto a la diagramación
  - conclusión: esta hermoso y que podríamos añadir cajas de texto, lo cual se profundizará para el examen

### pcb

[issue pcb](https://github.com/orgs/disenoUDP/projects/4/views/1?pane=issue&itemId=115279178&issue=disenoUDP%7Cdis8644-2025-1-proyectos%7C134)

- [issue 09](https://github.com/disenoUDP/dis8644-2025-1-proyectos/issues/134#issuecomment-2986132101)  
  - emisor: SebastianSaez1003  
  - enviado a: franudp del grupo 0c y docentes
  - temática: opiniones de pcb
  - conclusión: si hace alusión al sol, seria muy redundante, pero destacamos forma de lentes hacia atrás,

- [issue 10](https://github.com/disenoUDP/dis8644-2025-1-proyectos/issues/134#issuecomment-2986654634)  
  - emisor: clifford1one
  - enviado a: franudp del grupo 0c y docentes
  - temática: screw terminal y vector de lente
  - conclusión: toda la fuente de poder tuviera el mismo voltaje (9v) y footprints de la batería estan bien.

- [issue 11](https://github.com/disenoUDP/dis8644-2025-1-proyectos/issues/134#issuecomment-2989105082)  
  - emisor: clifford1one
  - enviado a: franudp del grupo 0c y docentes
  - temática: error con drc
  - conclusión: la pagina de jlcpcb salen las dimensiones mínimas para cada perforación, separación.

### carcasas

[issue carcasas](https://github.com/orgs/disenoUDP/projects/4/views/1?pane=issue&itemId=116136542&issue=disenoUDP%7Cdis8644-2025-1-proyectos%7C554)

- [issue 12](https://github.com/disenoUDP/dis8644-2025-1-proyectos/issues/554#issuecomment-2989115405)  
  - emisor: felix-rg416  
  - enviado a: grupo 06 y docentes
  - temática: medidas de pcb
  - conlusión: la pcb mide 100x50mm y también adjuntamos el repo en donde podrían ver la información completa

## Esquematico en Kicad (1 punto)

![Esquemático general](./imagenes/fps555-sch-general.png)

![Esquemático detalles](./imagenes/fps555-sch-detalle1.png)

![Esquemático detalles](./imagenes/fps555-sch-detalle2.png)

Nuestro proyecto "fps555" contiene un circuito PWM simulado con un chip 555, un motocontrolador L293D, un motorreductor de 6V 3RPM, un switch mts303 y un conector de batería.

El circuito PWM(pulse width modulation), que permite emular una onda análoga a través de señales digitales. Este genera señales a tal velocidad, que son percibidas como su promedio, lo que varía el ancho del pulso en su onda digital. Esto nos ayuda a regular la velocidad de motores DC,intensidad de un LED, entre otros.

El chip L293D es un doble puente H, el cual está diseñado para controlar motores con una corriente continua que permite controlar la dirección del giro del motor.

El switch mts303 tiene 6 pines, lo que permite mandar 2 señales a dos componentes distintos, de manera simultánea.

Un motorreductor es un motor de corriente continua (DC) que incluye una caja reductora, la cual permite disminuir las revoluciones por minuto; por esto, tiene una menor velocidad, pero sigue conservando fuerza.

Nuestro proyecto utiliza un PWM con un chip 555 para regular las RPM que tendrá nuestro motorreductor. El pin 3 del 555 está conectado al pin 1 del L293D. En el chip L293D tenemos que utilizar solo un puente H; eso quiere decir que utilizaremos solo una mitad del chip.

El switch mts303 ejerce dos funciones simultáneas; los pines 1, 2 y 3 corresponden al control de la dirección del motorreductor, donde el estado 1 se ejerce rotación en sentido horario, el estado 2 no deja pasar la corriente, es decir, está en estado "off" y en el estado 3 se ejerce rotación en sentido antihorario. Los pines 4, 5 y 6 del switch se ocuparon a modo de control del chip 555 al conectarlo directamente a su pin 4, donde el estado 1 y 3 dejan que fluya la corriente y funcione el resto del circuito, mientras que el estado 2 sería off. Usar este switch le da la ventaja al usuario de "encender" el circuito y activar el giro del motor con solo 1 movimiento.

Debido a que todos los esquemáticos de referentes para poder ocupar el chip L293D ocupaban diodos de seguridad en las conexiones hacia el motor que era controlado, se aplicó esta misma práctica como medida de precaución.

## PCB en Kicad (1 punto)

![PCB general](./imagenes/fps555-pcb-general.png)

![PCB detalles](./imagenes/fps555-pcb-detalle1.png)

![PCB detalles](./imagenes/fps555-pcb-detalle2.png)

![PCB 3D por delante](./imagenes/fps555-fRender.png)

![PCB 3D por delante](./imagenes/fps555-bRender.png)

## Recursos adicionales

[enlace a figma](https://www.figma.com/board/xtSdleNWkWIgJeE9Af27IX/fps555?node-id=0-1&p=f&t=aDNKgy5gH7pBcTs7-0)

en figma realizamos ideas rapidas y existe el proceso de nuestro proyecto

## Bibliografía

- [Datasheet de L293DNE](00-proyecto-02/grupo-06/datasheets/L293NE.PDF)
- PDF extraido de: <https://www.alldatasheet.es/datasheet-pdf/view/26889/TI/L293DNE.html>

- [Datasheet de 555 Presicion Timer](./grupo-06/datasheets/ne555.pdf)  
- PDF extraido de: <https://ti.com/lit/ds/symlink/ne555.pdf>
