# Cómo instalar servidor de CS:GO en Linux

_En este caso usaré Ubuntu 16.04 Server_

## Comenzando 🚀

_Para poder comenzar lo que tendreis que hacer es descargaros [Ubuntu Server 64-bits](http://releases.ubuntu.com/16.04/ubuntu-16.04.6-server-amd64.iso), o [Ubuntu Server 32-bits](http://releases.ubuntu.com/16.04/ubuntu-16.04.6-server-i386.iso). En este tutorial voy a seguir las instrucciones que podemos encontrar en [LGSM](https://linuxgsm.com/lgsm/csgoserver/)._

Mira **Deployment** para conocer como desplegar el proyecto.


### Pre-requisitos 📋

_En mi caso he montado 4 servidores de CS:GO para la Teleco LAN Party usando Proxmox, usando Ubuntu Server 64-bits, a cada servidor de CS:GO le he dedicado:_

* 2 Cores
* 2 GB de RAM
* 40 GB de memoria (para poder realizar al menos una copia de seguridad de cada servidor)

### Instalación 🔧

_A continuación vamos a ver los pasos que tenemos que seguir para realizar una correcta instalación del servidor._

_Primer paso: Instalar los programas necesarios para iniciar el servidor_

```
sudo dpkg --add-architecture i386; sudo apt update; sudo apt install mailutils postfix curl wget file bzip2 gzip unzip bsdmainutils python util-linux ca-certificates binutils bc jq tmux lib32gcc1 libstdc++6 libstdc++6:i386
```

_Segundo paso: Crearemos un usuario para la gestión del servidor, ya que no podemos iniciarlo con "sudo"_

```
adduser csgoserver
```

_Tercer paso: Nos loguearemos con el usuario que acabamos de crear_

```
su - csgoserver
```

_Cuarto paso: Descarga el instalador_

```
wget -O linuxgsm.sh https://linuxgsm.sh && chmod +x linuxgsm.sh && bash linuxgsm.sh csgoserver
```

_Quinto paso: Ejecuta el instalador, recuerda que NO puedes ejecutarlo como "sudo" y este se encuentra en la raiz del usuario "csgoserver"_

```
./csgoserver install
```

_Una vez acabado este proceso, tendrás que añadir un [TOKEN de STEAM](https://steamcommunity.com/dev/managegameservers)_

![](imagenes/gslt.gif)

_Finaliza con un ejemplo de cómo obtener datos del sistema o como usarlos para una pequeña demo_

## Ejecutando las pruebas ⚙️

_Explica como ejecutar las pruebas automatizadas para este sistema_

### Analice las pruebas end-to-end 🔩

_Explica que verifican estas pruebas y por qué_

```
Da un ejemplo
```

### Y las pruebas de estilo de codificación ⌨️

_Explica que verifican estas pruebas y por qué_

```
Da un ejemplo
```

## Deployment 📦

_Agrega notas adicionales sobre como hacer deploy_

## Construido con 🛠️

_Menciona las herramientas que utilizaste para crear tu proyecto_

* [Dropwizard](http://www.dropwizard.io/1.0.2/docs/) - El framework web usado
* [Maven](https://maven.apache.org/) - Manejador de dependencias
* [ROME](https://rometools.github.io/rome/) - Usado para generar RSS

## Contribuyendo 🖇️

Por favor lee el [CONTRIBUTING.md](https://gist.github.com/villanuevand/xxxxxx) para detalles de nuestro código de conducta, y el proceso para enviarnos pull requests.

## Wiki 📖

Puedes encontrar mucho más de cómo utilizar este proyecto en nuestra [Wiki](https://github.com/tu/proyecto/wiki)

## Versionado 📌

Usamos [SemVer](http://semver.org/) para el versionado. Para todas las versiones disponibles, mira los [tags en este repositorio](https://github.com/tu/proyecto/tags).

## Autores ✒️

_Menciona a todos aquellos que ayudaron a levantar el proyecto desde sus inicios_

* **Andrés Villanueva** - *Trabajo Inicial* - [villanuevand](https://github.com/villanuevand)
* **Fulanito Detal** - *Documentación* - [fulanitodetal](#fulanito-de-tal)

También puedes mirar la lista de todos los [contribuyentes](https://github.com/your/project/contributors) quíenes han participado en este proyecto. 

## Licencia 📄

Este proyecto está bajo la Licencia (Tu Licencia) - mira el archivo [LICENSE.md](LICENSE.md) para detalles

## Expresiones de Gratitud 🎁

* Comenta a otros sobre este proyecto 📢
* Invita una cerveza 🍺 a alguien del equipo. 
* Da las gracias públicamente 🤓.
* etc.



---
⌨️ con ❤️ por [Villanuevand](https://github.com/Villanuevand) 😊

