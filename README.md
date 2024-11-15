# PRACTICA-6

## Introducción
En este laboratorio, se controló un motor a pasos utilizando un Arduino Uno y un driver de motor a pasos. El objetivo principal fue aprender cómo generar los pulsos necesarios para controlar la velocidad y 
dirección del motor, y cómo interactuar con el driver a través de la programación en Arduino. Los motores a pasos son ampliamente utilizados en aplicaciones que requieren movimientos precisos, como la robótica
y la automatización.

## Instrucciones
Una vez elaborado el código que permitirá controlar el motor a pasos se procede con:
1.- Se conecta el motor al driver, asegurándose de que las conexiones de alimentación y control estén correctas.
2.- Cargar el código proporcionado en el Arduino Uno.
3.- Observar el movimiento del motor, que se moverá en una dirección durante 5 ciclos y luego en la dirección opuesta durante 3 ciclos, con una pausa de 1 segundo entre los cambios de dirección.

El código que se implementó para ejecutar la tarea es el siguiente:

```
#define pulsos 801

#define sentido 2
#define pasos 3

void setup() {
  pinMode(sentido, OUTPUT);
  pinMode(pasos, OUTPUT);
  Serial.begin(9600);
}

void loop() {
  // put your main code here, to run repeatedly:
  digitalWrite(sentido, LOW);
  for (int i=0; i<5*pulsos; i++){
      digitalWrite(pasos, HIGH);
      delayMicroseconds(500);
      digitalWrite(pasos, LOW);
  }
  digitalWrite(sentido, HIGH);
  delay(1000);
  for (int i=0; i<3*pulsos; i++){
      digitalWrite(pasos, HIGH);
      delayMicroseconds(416);
      digitalWrite(pasos, LOW);
  }
  delay(1000);
}
```

- El código define dos pines, el pin 2 para controlar la dirección del motor y el pin 3 para generar los pulsos que controlan el avance de los pasos.
- En el setup() se configuran ambos pines como salida
- Dentro del loop se tiene dos ciclos "for", en el primero se usa un delay de 500 microsegundos, esto para que las 5 vueltas se ejecuten en 2 segundos,
  mientras que en el otro for se usa un delay de 426 microsegundos, esto hará que las 3 vueltas se ejecuten en 1 segundo.

  ## Conclusiones
  - *Edgar Zahid Hernandez Garcia:*

- *Gael Mateo Rangel Chavez:*
En conclusión, esta práctica laboratorio permitió controlar un motor a pasos utilizando un Arduino Uno y un driver, aplicando los conceptos de pulsos y control de dirección. Se programaron ciclos para mover el motor en dos direcciones con diferentes velocidades, ajustando el retardo entre pulsos para modificar la velocidad del motor. Los cálculos de tiempo confirmaron que el motor completa las 5 y 3 vueltas en aproximadamente 2 y 1 segundo, respectivamente. Este ejercicio demuestra cómo se pueden controlar con precisión los motores a pasos en aplicaciones robóticas y de automatización con un Arduino.

- *Alejandro Saldaña Garcia:*
