# Practica ESP32 con DHT22
Este repositorio muestra como podemos programar una ESP32 con el sensor DHT22 para medir temperatura y humedad.

## Introducción

### Descripción

La ```Esp32``` la utilizamos en un entorno de adquision de datos, lo cual en esta practica ocuparemos un sensor (```DTH22```) para adquirir temperatura y humedad del entorno; Cabe aclarar que esta practica se usara un simulador llamado [WOKWI](https://https://wokwi.com/).


## Material Necesario

Para realizar esta practica necesitas lo siguiente

- [WOKWI](https://https://wokwi.com/) como simulador.
- Tarjeta ```ESP 32```.
- Sensor ```DHT22```.



## Instrucciones

### Requisitos previos

Para poder usar este repositorio necesitas entrar a la plataforma [WOKWI](https://https://wokwi.com/).


### Instrucciones de preparación de entorno 

1. Entramos al simulador [WOKWI](https://https://wokwi.com/) y selecionamos la tarjeta ```ESP 32``` como se muestra en la siguiente imagen.

![](https://github.com/jorgelopezquiroz/PracticaESP32-DHT22/blob/main/Captura%20de%20Pantalla%202023-06-09%20a%20la(s)%2020.45.49.png?raw=true)


2. Posteriormente se abrirá la terminal de programación y se coloca la siguente programación:

```
#include "DHTesp.h"


const int DHT_PIN = 15;
DHTesp dhtSensor;


void setup() {

  Serial.begin(115200);
  dhtSensor.setup(DHT_PIN, DHTesp::DHT22);
}

void loop() {

  TempAndHumidity  data = dhtSensor.getTempAndHumidity();
  Serial.println("Temp: " + String(data.temperature, 1) + "°C");
  Serial.println("Humidity: " + String(data.humidity, 1) + "%");
  Serial.println("---");
  delay(1000);
}

```
3. Se necesita instalar la libreria de **DHT sensor library for ESPx** en el simulador como se muestra en la siguiente imagen.
![](https://raw.githubusercontent.com/jorgelopezquiroz/PracticaESP32-DHT22/ca51481f5635f53bad3ed4a820218477dcddbf1b/Captura%20de%20Pantalla%202023-06-09%20a%20la(s)%2020.35.46.png)
 
4. Hacer la conexion de **DHT22** con la **ESP32** como se muestra en la siguente imagen.

![](https://github.com/jorgelopezquiroz/PracticaESP32-DHT22/blob/main/Captura%20de%20Pantalla%202023-06-09%20a%20la(s)%2020.37.37.png?raw=true)

### Instrucciónes de operación

1. Iniciar la simulación.
2. Visualizar los datos en el monitor serial.
3. Colocar la temperatura y humedad dando *doble click* al sensor **DHT22** 

## Resultados

Cuando haya compilado, verás los valores dentro del monitor serial como se muestra en la siguente imagen.

![](https://raw.githubusercontent.com/jorgelopezquiroz/PracticaESP32-DHT22/74dfee88e0221bd9961b6cd222216a97d69b7e05/Captura%20de%20Pantalla%202023-06-09%20a%20la(s)%2020.57.24.png)




## Evidencias
![](https://raw.githubusercontent.com/jorgelopezquiroz/PracticaESP32-DHT22/8e2978a598aae573cc3a88f3d52be1ae1c6acedd/Captura%20de%20Pantalla%202023-06-09%20a%20la(s)%2020.56.41.png)



# Créditos

Desarrollado por Jorge Esteban Lopez Quiroz

- [GitHub](https://github.com/jorgelopezquiroz)