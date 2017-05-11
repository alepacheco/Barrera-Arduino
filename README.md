# Proyecto de Informática
## Prototipo de Cruce de Ferrocarril

### Listado de componentes usados en el proyecto:
- 1 LED Rojo
- 1 LED Verde
- 1 LED Amarillo
- 1 Servo
- 1 Resistencias de 220 ohmmios
- 1 Arduino UNO
- 1 Placa de prototipos
- Cables

## Construcción de la barrera
Procederemos seguidamente al montaje de la barrera. Para ello hemos dibujado sobre un cartón el desarrollo y lo hemos recortado con algunos huecos.


En la parte frontal del semáforo hemos adaptado un agujero con las medidas de nuestro servo. Con los propios tornillos que venían en nuestro kit para adaptar las piezas en nuestro serio los usamos para fijar el servo contra el cartón.

En la parte de abajo habremos recortado unas franjas para poder ensamblar una base y que el poste gane estabilidad.

En la parte superior hemos usado una aguja de coser para realizar los agujeros por donde meteremos las patas de los LEDs.

El poste por dentro es hueco para poder esconder los cables y que el resultado final del mismo sea lo más estético posible.


Una vez ensamblado todo quedaría como la imagen de la derecha, donde hemos fijado las patas del poste, hemos insertado y colocado los LEDs y hemos colocado la barrera.

Ésta última la hemos fabricado con el mismo cartón que nos quedaba, utilizando también un tornillo para fijarla sobre el servo de la siguiente manera:

Un tornillo para fijar un extremo de la barrera sobre el eje de rotación del servo. Previamente el servo lo hemos equipado con una de las barras que vienen en nuestro kit para poder atornillar. El segundo tornillo sobre la barrera lo hemos fijado a una cierta distancia del eje de rotación por detrás de la barrera. De esta manera evitaremos que la barrera se escurra o pivote sobre el eje de rotación del servo (primer tornillo).


## Codigo usado
```
#include <Servo.h> //Importamos la biblioteca Servo.h
#include <Arduino.h>

Servo barrera; //Declaramos un servo y se llama barrer, con esto vamos a trabajar
int ledv = 13; //Declaramos un Led, en este caso el verde sobre el pin 13
int leda = 12;
int ledr = 11;

//Establecemos el modo de función de cada led
void setup() {
    pinMode(ledv, OUTPUT);
    pinMode(leda, OUTPUT);
    pinMode(ledr, OUTPUT);
}   

void loop() {
    //Comenzamos nuestro programa encendiendo el Led rojo ya que nuestra barrera comien//za con la posición 0.
    //Esto es ajustable dado que nosotros decidimos las posiciones iniciales
    digitalWrite(ledr, HIGH); //Le mandamos un angulo de 10 grados a nuestro servo por errores de funcionamiento.
    //Recomiendo que el inicio del mismo sea en 0 grados
    barrera.write(10);
    //Hacemos un delay de 5 segundo antes de mandarle la siguiente instruccion
    delay (5000);
    //Hacemos el programa para el cambio de rojo a verde pasando por el amarillo.
    digitalWrite(ledr, LOW);
    digitalWrite(leda, HIGH);
    delay(1000);
    digitalWrite(leda, LOW);
    delay(1000);
    digitalWrite(leda, HIGH);
    delay(1000);
    digitalWrite(leda, LOW);
    delay(1000);
    digitalWrite(leda, HIGH);
    delay(1000);
    digitalWrite(leda, LOW);
    delay(1000);
    digitalWrite(ledv, HIGH);
    //Una vez ha cambiado el led a verde, cambiamos la posición de la barrera.
    barrera.write(100);
    delay(5000);
    digitalWrite(ledv, LOW);  
    }
```
Por último os dejamos el prometido vídeo con el funcionamiento de la barrera:
![alt text](http://2.bp.blogspot.com/-guCqR4duKKw/UwCep_MX57I/AAAAAAAAAIc/DAgdaZCxtcs/s1600/DSC00238.JPG "Logo Title Text 1")


### Por Alejandro, Hellin, Adrian y Daniel
