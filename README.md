
# SERVIDOR DE AUDIOS SOBRE RASPBERRY PI

Se trata de combinar varios servicios sobre una Raspberry como servidor de audio, para ellos uso algunos proyectos de terceros o otros propios

![screen shot](screenshot.png)

Un servicio textToAudio con un interface web que permite convertir texto a audio, detalle de este servicio en https://github.com/manologcode/text_to_mp3_pi  

Un segundo servicio  permite descargar audios de Youtube mas detalle del proyecto en https://github.com/manologcode/audio_youtube

El imprescindible Filebrowser como gestor de archivos para subir o descargar.

RPI-Monitor como servicio para controlar el estado de nuestra rapsberry este 
Para instalar RPI-Monitor tienes que instalar los paquetes apt-transport-https y ca-certificates si es que no los tienes ya instalados, añadir el repositorio ya que RPI-Monitor no está en los repositorios oficiales de Raspbian, añadir las claves del repositorio, actualizar el listado de paquetes e instalar el paquete rpimonitor.

Todo esto lo puedes hacer ejecutando las siguientes órdenes (de una en una):

sudo apt-get install apt-transport-https ca-certificates
sudo wget https://goo.gl/vewCLL -O /etc/apt/sources.list.d/rpimonitor.list
sudo apt-key adv --recv-keys --keyserver keyserver.ubuntu.com 2C0D3C0F
sudo apt update
sudo apt install rpimonitor

Y todos estos audios están disponible a traves de Navidrome como listas y reproductor.

Y una pagina de arranque a modo de menu para acceder a los servicios

## instalación

Debemos de tener un Rapsberry con docker y docker-compose instalado si no sabes como en este post esta explicado. https://manolog.es/blog/2022/03/14/rapsberry-pi-sever-primeros-pasos/

Mi raspberry lo tengo con una ip fija en 192.168.1.100, si la tuya es diferente, deberás de cambiar el docker-compose.yml y el menu.js de statPage

para ejecutarlos simplemente ejecutar:

```

git clone https://github.com/manologcode/server_pi_audio.git
mv server_pi_audio/* .
rm -rf server_pi_audio 

docker-compose up -d

```

y entrado en tu navegador a http://192.168.1.100