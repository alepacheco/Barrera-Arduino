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
```c
#include <Servo.h>
#include <Arduino.h>

#define LED_VERDE 13
#define LED_AMARILLO 12
#define LED_ROJO 11
#define PIN_PITO 10
#define PIN_SERVO 9

#define ROJO led(1);
#define AMARILLO led(2);
#define VERDE led(3);

#define BARRERA_SUBIDA 75
#define BARRERA_BAJADA 10

Servo barrera;

void setup(){
   pinMode(LED_VERDE,OUTPUT);
   pinMode(LED_AMARILLO, OUTPUT);
   pinMode(LED_ROJO, OUTPUT);
   pinMode(PIN_PITO,OUTPUT);
   barrera.attach(PIN_SERVO);
   bajar();
}
void loop(){
  ROJO
  delay(4000);
  AMARILLO
  delay(2000);
  subir();
  VERDE
  delay(5000);
  bajar();
  ROJO
}

void bajar() {
  for (int x = BARRERA_SUBIDA; x > BARRERA_BAJADA;x--) {
    barrera.write(x);
    delay(5);
  }

}

void subir() {
  for (int x = BARRERA_BAJADA; x < BARRERA_SUBIDA; x++) {
    barrera.write(x);
    delay(5);
  }
}


void led(int x) {
  if (x== 1){
     digitalWrite(LED_ROJO, HIGH);
     digitalWrite(LED_AMARILLO, LOW);
     digitalWrite(LED_VERDE, LOW);
  }
  if (x== 2){
     digitalWrite(LED_ROJO, LOW);
     digitalWrite(LED_AMARILLO, HIGH);
     digitalWrite(LED_VERDE, LOW);
  }
  if (x== 3){
     digitalWrite(LED_ROJO, LOW);
     digitalWrite(LED_AMARILLO, LOW);
     digitalWrite(LED_VERDE, HIGH);
  }
}

```
Por último os dejamos el prometido vídeo con el funcionamiento de la barrera:
![alt text](http://2.bp.blogspot.com/-guCqR4duKKw/UwCep_MX57I/AAAAAAAAAIc/DAgdaZCxtcs/s1600/DSC00238.JPG "Logo Title Text 1")


### Por Alejandro, Hellin, Adrian y Daniel
