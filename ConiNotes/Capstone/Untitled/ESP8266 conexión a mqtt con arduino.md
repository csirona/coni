El proyecto ESP8266 conexion a mqtt con arduino esta planteado para enviar mensajes al servidor mosquitto donde esxplicamos el paso a paso

## Acerca del proyecto

En este post vamos a hacer la primera conexión entre mqtt usando como servidor mosquitto y el esp8266-01 conectado al arduino, se va a explicar paso a paso que se necesita para poder enviar un mensaje y poderlo visualizar por el momento en la terminar serial.

El alcance de este post es poder conectar el esp8266 a la red wifi, crear en local el servidor habilitando el protocolo mqtt y poder crear un topic para que se pueda suscribir el broker y enviar mensajes, en post futuros vamos a tomas la información que nos llega y manipularla.

## Conocimiento previo

Antes de iniciar debemos tener en cuenta los siguientes post para avanzar con el esp8266 y su conexión, aunque se explicara paso a paso, recomiendo dar un repaso de los temas que menciono a continuación.

|Post|Descripción|
|---|---|
|[Datasheet ESP8266](http://codigoelectronica.com/blog/esp8266-esp01-datasheet)|Como vamos a trabajar con el esp8266 es bueno tener en cuenta sus características, pines y conexiones.|
|[Conectar ESP8266](http://codigoelectronica.com/blog/conectar-esp8266-esp-01)|La primera conexión que vamos a realizar con el ESP8266 es para cargar el firmware, pero debemos verificar que el modulo este funcionando, para ello este post explica como conectar el modulo vía USB-serial.|
|[ESP8266 flasher firmware](http://codigoelectronica.com/blog/esp8266-flasher-firmware)|Uno de los pasos es cargar el firmware apropiado para la esp8266, recomiendo dar un repaso a este post.|
|[Mosquitto server](http://codigoelectronica.com/blog/mosquitto-server)|Antes de iniciar debemos conocer el servidor quien sera el encargado de recibir la información, sus características y como instarlo en los diferentes sistemas operativos.|

## Materiales

### Software

Para el desarrollo de este proyecto vamos a requerir los siguientes programas, librerías e instaladores, a continuación encontrara los link para que los descargue y los post donde podrá realizar la instalación.

|Software|Descripción|Link|
|---|---|---|
|Arduino|   |   |
|Software flasher esp8266|Encontrara el firmware y el programa para poder hacer el flasher del esp.|[ESP8266 software](https://github.com/codigoelectronica/esp8266-software)|
|PubSubClient|Esta biblioteca proporciona un cliente para realizar mensajes simples de publicación/suscripción con un servidor que admita MQTT.|[pubsubclient por Nick O'Leary](https://pubsubclient.knolleary.net/)|
|WiFiEsp|La líbreria WiFiEsp permite que la placa arduino se conecte a intenet.|[WiFiEsp por bportaluri](https://github.com/bportaluri/WiFiEsp)|
|Otros instaladores|   |   |
|Instalar mosquitto|Tenemos unos post en donde explicamos la instalación de mosquitto con el protocolo mqtt, y en donde se realizan las primeras pruebas, recomiendo realizar este post antes de continuar.|- [Instalar mosquitto en ubuntu](http://codigoelectronica.com/blog/instalar-mosquitto-ubuntu)<br>- [Instalar mosquitto en windows](http://codigoelectronica.com/blog/instalar-mosquitto-windows)|

### Componentes electrónicos

|Material|Cantidad|Descripción|
|---|---|---|
|Arduino|1|Cualquier placa arduino podemos trabajar|
|ESP8266-01|1|Modulo de conexión a intener|
|Cables de conexión|Los que necesite|Generalmente cables macho a macho|