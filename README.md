# Cómo instalar SteamCache en Linux (Fedora Server 29)

_En este caso usaré Ubuntu 18.04 Server_

## Comenzando 🚀

_Para poder comenzar lo que tendreis que hacer es descargaros [Fedora Server 30](https://download.fedoraproject.org/pub/fedora/linux/releases/30/Server/x86_64/iso/Fedora-Server-dvd-x86_64-30-1.2.iso), y [Rufus](https://rufus.ie/es_ES.html) para montar un USB para instalar Fedora en el servidor._

## Pre-requisitos 📋

_Nuestro SteamCache tiene los siguientes componentes:_

* Xeon E54030
* 8 GB de RAM
* 500 GB HDD
* 3 TB HDD, exclusivo para almacenar los juegos.

## Instalación 🔧

_A continuación vamos a ver los pasos que tenemos que seguir para realizar una correcta instalación._

_**Primer paso:** Instalar Fedora en el servidor siguiendo el asistente, antes de ello tenemos que montar la ISO de Fedora en el USB a través de Rufus_

1. Pinchamos el USB en el PC y lo abrimos.
2. Install Fedora 30
3. Seleccionamos idioma y le damos a continuar
4. Elegimos el destino de instalación, dentro seleccionamos el disco y le damos a siguiente.
5. Pulsamos sobre "Eliminar todo" y reclamar espacio.
6. Y pulsamos sobre empezar instalación.
7. Ponemos el nombre del equipo, en nuestro caso, steamcache y le damos a comenzar.
8. Completamos los datos que nos piden. Y esperamos a que la instalación finalice.


_**Segundo paso:** Desinstalamos versiones anteriores de DOCKER_

```
sudo dnf remove docker \
                docker-client \
                docker-client-latest \
                docker-common \
                docker-latest \
                docker-latest-logrotate \
                docker-logrotate \
                docker-selinux \
                docker-engine-selinux \
                docker-engine
```

_**Tercer paso:** Instalamos DOCKER_

```
sudo dnf -y install dnf-plugins-core

sudo dnf config-manager --add-repo https://download.docker.com/linux/fedora/docker-ce.repo

sudo dnf install docker-ce docker-ce-cli containerd.io

sudo usermod -aG docker sc
```

_**Cuarto paso:** Finalizamos la instalación_

```
sudo usermod -aG docker sc
sudo systemctl enable docker
```
Donde sc es el usuario con el que queremos ejecutar docker


_**Quinto paso:** Reiniciamos el servidor y hacemos la prueba_

```
docker run hello-world
```

_**Sexto paso:** Instalamos COCKPIT. Una vez instalado volvemos a reiniciar el servidor_

```
sudo dnf install cockpit-docker
```

_Una vez acabado este proceso, tendrás que añadir un [Steam Game Server Login Token (GSLT)](https://steamcommunity.com/dev/managegameservers)_

![](imagenes/gslt.gif)

_Si no sabes dónde añadir el GSLT haz [click aquí.](https://github.com/aruznieto/CSGO_Server/wiki/%C2%BFC%C3%B3mo-a%C3%B1ado-o-cambio-el-GSLT%3F)_

## Ejecutando las pruebas ⚙️
_Para saber si tu servidor se está ejecutando correctamente o te da algún fallo que no sabes solucionar puedes poner lo siguiente._
```
./csgoserver debug
```
_Ahí te dirá que es lo que está fallando. Si tienes algún otro problema, no dudes en comentarlo._


## Gestionar tu servidor ✔️

_Para INICIAR tu servidor simplemente tendrás que poner:_
```
./csgoserver start
```

_Para PARAR tu servidor simplemente tendrás que poner:_
```
./csgoserver stop
```

_Para REINICIAR tu servidor simplemente tendrás que poner:_
```
./csgoserver restart
```

_Para ver si tu servidor se está ejecutando pon:_
```
./csgoserver details
```
_Ahí podrás ver la contraseña y la RCON de tu servidor (si la has puesto), los puertos y la IP que usa, y mucha más información

## Construido con 🛠️

* [Ubuntu](https://www.ubuntu.com/download/server/thank-you?version=18.04.2&architecture=amd64)
* [LGSM](https://linuxgsm.com/lgsm/csgoserver/)

## Wiki 📖

Puedes encontrar mucho más de cómo configurar el servidor en nuestra [Wiki](https://github.com/aruznieto/CSGO_Server/wiki)

## Autores ✒️

* **Andrés Ruz Nieto** - *Documentación* - [aruznieto](https://github.com/aruznieto) 
* **Rafael García Tristante** - *Documentación* - [TheMrRafus](https://github.com/TheMrRafus) 

## Expresiones de Gratitud 🎁

* Comenta a otros sobre este proyecto 📢
* Invita una cerveza 🍺 a alguien del equipo. 
* Da las gracias públicamente 🤓.
* etc.

---
⌨️ con ❤️ por [aruznieto](https://github.com/aruznieto) y [TheMrRafus](https://github.com/TheMrRafus) 😊
