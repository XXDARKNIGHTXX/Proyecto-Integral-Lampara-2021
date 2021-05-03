# Proyecto-Integral-Lampara-2021

* Aqui esta mi primera representación del proyecto nuevo de Lampara

* En el que consiste en hacer un proyecto de lampara para el David 

* Ahora te pondre el codigo de Arduino k he hecho con Marc:)

![CasePlansVictor](https://raw.githubusercontent.com/XXDARKNIGHTXX/Proyecto-Integral-Lampara-2021/269936f4360b578557f9ade212bb5d039e2892b6/caseplansVictor.svg)

![Proyecto de ARDUINO LEDS Y POCIMERTO]()

``` C++

  
  
  
 const int led1pin = 3;
const int led2pin = 5;
const int led3pin = 6;
const int pinBoton = 2;
const int pinPotenciometro = A0;

int valorPotencimetro= 0;
int valorIntensidad = 0;


int estadoBoton = 0;
int estadoPrevioBoton = 0;

bool encenderLeds = false;

void setup() {
  // declare the LED pins as outputs
  pinMode(led1pin, OUTPUT);
  pinMode(led2pin, OUTPUT);
  pinMode(led3pin, OUTPUT);  

  // declare the switch pin as an input
  pinMode(2, INPUT);
}

void loop() {
 leerBoton();
 leerPotenciometro(); 
 encender();
}

void leerBoton() {
  

  estadoBoton = digitalRead(2);

  if (estadoBoton == HIGH && estadoPrevioBoton == LOW) {
     encenderLeds = !encenderLeds;
  }

  estadoPrevioBoton = estadoBoton;
  
}

void leerPotenciometro()
{
  valorPotencimetro = analogRead(pinPotenciometro);

  valorIntensidad = valorPotencimetro/4;

 
}


void  encender() {
 if(encenderLeds){
  analogWrite(led1pin,valorIntensidad);
  analogWrite(led2pin,valorIntensidad);
  analogWrite(led3pin,valorIntensidad);

 }
 else{
  digitalWrite(led1pin, LOW);
  digitalWrite(led2pin, LOW);
  digitalWrite(led3pin, LOW);
 }
  
}



![Captura de Pantalla de mi ARDUINO hecho por mi](https://raw.githubusercontent.com/XXDARKNIGHTXX/Proyecto-Integral-Lampara-2021/main/WhatsApp%20Image%202021-05-03%20at%2012.36.53.jpeg)
