# educational-robot-autoreversible #

> RC robot autoreversible for educational use  

* * *

## Resumen ##

Robot radiocontrolado diseñado por los alumnos de la actividad de robótica
[Taller de Inventores](http://tallerinventores.github.io/). Ha sido desarrollado
y optimizado para impresión 3D y pensando en su bajo coste y facilidad de
montaje y uso.

## Instalación ##

En esta sección se cubre la instalación de software y hardware para el montaje
recomendado, mediante [Scratch](https://scratch.mit.edu/) y
[Arduino](http://www.arduino.cc/).

### Requerimientos de software ###

Para poder usar Scratch (v2.0 online) con Arduino, es necesario
[s2a_fm](https://github.com/MrYsLab/s2a_fm) una extensión de Scratch para
comunicarse con Arduino. Para generar los archivos aptos para la impresora 3D
desde los archivos `.stl` será necesario adicionalmente un software para esta
función, como puede ser [Slic3r](http://slic3r.org/).

### Requerimientos de hardware ###

Será necesario para su montaje y uso cuatro pilas tipo AA, cuatro motores con
reductora en miniatura, un sensor de proximidad por infrarrojos basado en
TCRT5000, una placa Robgednaut Zond con un Arduino Nano o compatible y un módulo
de bluetooth HC05. Adicionalmente hará falta tornillería variada de métrica
tres. Se recomienda un macho de misma métrica.  

## Uso ##

Instrucciones de montaje y puesta en marcha.

### Montaje del robot ###

1.  Imprimir una unidad de los archivos `internal.stl` e `internal-sensor.stl`.
    Imprimir dos unidades de `external-side.stl`. Imprimir cuatro unidades de 
    `leg.stl`. Puede ser necesario repasar las piezas impresas con el fin de
    eliminar rebabas.  
2.  Montar el sensor de proximidad en la pieza que permite su montaje
    (_internal-sensor_), fijándolo con un tornillo para plástico de diez
    milímetros de largo.  
3.  Fijar las dos partes interiores entre sí (_internal-sensor_ e _internal_),
    repasando los agujeros de una de las mitades para tres milímetros de
    diámetro, y hacer rosca en los correspondientes de la otra mitad. Atornillar
    ambas mitades con cuatro tornillos de métrica tres por veinticinco.  
4.  Colocar cada uno de los motores en las aperturas del chasis externo
    (_external-side_). Fijarlos en su posición con tornillos de cabeza hexagonal
    de métrica tres por veinte y una tuerca en el lado opuesto, o bien usando
    bridas.  
5.  Cerrar uno de los extremos del robot usando cuatro tornillos de métrica tres
    por treinta con una arandela, previa rosca en los agujeros de la mitad
    central.  
6.  Realizar todas las uniones eléctricas y meter todo el hardware necesario en
    el interior del chasis del robot.  
7.  Usar cuatro tornillos de métrica tres por treinta con arandela para cerrar
    el robot con la parte externa restante.  

### Conexión eléctrica ###

Este proyecto usa [Robgednaut](http://akornsys-rdi.github.io/robgednaut/) Zond
como placa de conexionado, si no dispones de ella puedes ver su esquema de
conexiones en la página oficial.  

Las alimentaciones para todos los dispositivos las provee la placa de control.
El cable de señal analógica del sensor de proximidad infrarrojo se conecta a A.
Los motores de cada lado van conectados en paralelo y a su vez a un canal de la
salida para motores, respetando su polaridad.

### Firmware ###

El Arduino deberá tener cargado el firmware Firmata (incluido con Arduino IDE
bajo en nombre de StandardFirmata).  

### Software ###

Con la comunicación bluetooth establecida (elementos emparejados), lanzar s2a_fm
con el nombre del puerto donde realizar la comunicación por bluetooth. Por
ejemplo:

        python s2a_fm.py /dev/rfcomm0

Abrir Scratch y cargar el proyecto educational-robot-autoreversible.sb2, una vez
hecho, se podrá ver en la interfaz gráfica los posibles movimientos del robot en
forma de flechas para dichas órdenes.

El robot avanzará en la dirección elegida hasta que sea detenido o cambiado de
dirección. El robot puede detenerse con el botón en forma de X. El botón
circular de paro de emergencia permite cancelar cualquier orden, deshabilitar el
robot y parar el programa. Después de pulsarlo será necesario volver a iniciar
el proyecto de Scratch.  

### Bugs ###

Se han observado los siguientes problemas:  

-   Debido a todo el hardware que va dentro del robot, ha sido necesario
    espaciar las partes para ganar espacio.  
-   El interruptor de encendido/apagado es difícil de accionar al quedar dentro
    de la estructura.  
-   El sotfware de control provoca al inicio movimientos extraños.  

## Enlaces externos ##

Este proyecto también está presente en:  

-   [Scratch](https://scratch.mit.edu/projects/112577118/).  
-   [Thingiverse](http://www.thingiverse.com/thing:1656800).  

## Créditos ##

Proyecto realizado por Taller de Inventores 2016, representado por:  

-   kwendenarmo <kwendenarmo@akornsys-rdi.net>  

Alumnos del Centro de Formación Padre Piquer:  

-   C, Duanju  
-   S, Saúl  
