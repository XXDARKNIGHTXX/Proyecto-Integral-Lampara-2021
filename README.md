# Proyecto-Integral-Lampara-2021

* Aqui esta mi primera representación del proyecto nuevo de Lampara

* En el que consiste en hacer un proyecto de lampara para el David 

* Ahora te pondre el codigo de Arduino k he hecho con Marc:)

* ![CasePlansVictor](https://raw.githubusercontent.com/XXDARKNIGHTXX/Proyecto-Integral-Lampara-2021/269936f4360b578557f9ade212bb5d039e2892b6/caseplansVictor.svg)

* ![Proyecto de ARDUINO LEDS Y POCIMERTO]

* ¿Qué quiero con esta lampara?

Usar la como luz de mesa de noche o de escritorio

* ¿Como de grande sera?

De 15cm por 15cm de ancho y alto mas o menos eso se ira viendo a lo largo del proyecto

* ¿Que efectos tendra?

 * Simple iluminación

* ¿Como quiero que actue?

Quiero que se encienda y apague con el boton que tendra en un lado de la base al lado de las piedritas

![Abujero de la Caja](https://raw.githubusercontent.com/XXDARKNIGHTXX/Proyecto-Integral-Lampara-2021/ab6b713f54ae19e59800ef9bedb5e0f763dadf49/Abujero.svg)

![Vidrio Victor Y Foto De Javi](https://raw.githubusercontent.com/XXDARKNIGHTXX/Proyecto-Integral-Lampara-2021/dbc21aa7893c9dce91d02dc8f0799030a8e94a4e/VIDRIO%20VICTOR.svg)

![Vidrioo Victor Blanco Y Negro](https://raw.githubusercontent.com/XXDARKNIGHTXX/Proyecto-Integral-Lampara-2021/31a5d05e8e484498d80fd7212daa0a0539baa431/VIDRIO%20VICTOR%2001.svg)

![Caja numero 6](https://raw.githubusercontent.com/XXDARKNIGHTXX/Proyecto-Integral-Lampara-2021/bbdf8886fee60ecdaa03b3dfdfa09bd984b10a92/caja%20dia%206.svg)



Aqui he hecho el abujero de la caja que me pediste.

Cuanto mide de alto?

* mide 130 de alto

Cuanto mide de ancho?

* y mide 40 





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

