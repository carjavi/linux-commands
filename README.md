<p align="center"><img src="./img/Terminal.webp" height="200" alt=" " /></p>
<h1 align="center"> linux Commands</h1> 
<h4 align="right">February 24</h4>

<br>
<img src="https://img.shields.io/badge/OS-Linux%20GNU-yellowgreen">

<img src="https://img.shields.io/badge/OS%20-Raspbian%20GNU%2FLinux%2011%20(bulleye)-yellowgreen">

<img src="https://img.shields.io/badge/OS%20-Raspbian%20GNU%2FLinux%2010%20(buster)-yellowgreen">

<img src="https://img.shields.io/badge/OS-Linux%20GNU-yellowgreen">
<img src="https://img.shields.io/badge/Hardware-Raspberry%20ver%204-red">
<img src="https://img.shields.io/badge/Hardware-Raspberry%203B%2B-red">
<img src="https://img.shields.io/badge/Hardware-Raspberry%20Zero-red">

<br>

# Table of Contents
- [Table of Contents](#table-of-contents)
- [Update \& upgrade](#update--upgrade)
- [Syststem Information Commands](#syststem-information-commands)
  - [Busqueda](#busqueda)
- [echo](#echo)
- [On terminal](#on-terminal)
  - [Busqueda con filtro](#busqueda-con-filtro)
- [Use of wget](#use-of-wget)
- [Cómo gestionar procesos](#cómo-gestionar-procesos)
  - [Mostrar todos los procesos](#mostrar-todos-los-procesos)
  - [Cerrar un proceso](#cerrar-un-proceso)
  - [Forzar cierre de proceso por PID](#forzar-cierre-de-proceso-por-pid)
  - [Gestionar procesos en el fondo](#gestionar-procesos-en-el-fondo)
  - [Iniciar proceso en background](#iniciar-proceso-en-background)
  - [Poner procesos en background](#poner-procesos-en-background)
  - [Mostrar procesos en background](#mostrar-procesos-en-background)
  - [Traer al frente proceso](#traer-al-frente-proceso)
  - [How to use wget to download files and interact with rest APIs](#how-to-use-wget-to-download-files-and-interact-with-rest-apis)
  - [Sending GET requests](#sending-get-requests)
- [Modificación de permisos de ficheros en Linux](#modificación-de-permisos-de-ficheros-en-linux)
  - [El comando chmod](#el-comando-chmod)
  - [Usar opciones con los comandos chmod y chown](#usar-opciones-con-los-comandos-chmod-y-chown)
  


<br>

# Update & upgrade
```sudo apt-get update && sudo apt-get upgrade```<br>
```-h, --help```
           Muestra un mensaje corto sobre el uso.

```-y, --yes, --assume-yes```
           Supone una respuesta afirmativa a todas las preguntas, de esta forma apt-get se
           ejecuta sin necesidad de intervención posterior para tomar decisiones.  apt-get
           terminará sin hacer nada de producirse una situación no deseada, como cambiar un
           paquete retenido, instalar un paquete sin autenticar o desinstalar un paquete
           esencial. Opción de configuración: APT::Get::Assume-Yes.

```-V, --verbose-versions```
           Muestra las versiones completas para los paquetes actualizados e instalados. Opción de
           configuración: APT::Get::Show-Versions.

```--show-progress```
           Show user friendly progress information in the terminal window when packages are
           installed, upgraded or removed. For a machine parsable version of this data see
           README.progress-reporting in the apt doc directory. Configuration Item:
           DpkgPM::Progress and Dpkg::Progress-Fancy.

```--force-yes```
           Supone una respuesta afirmativa a todas las preguntas. Ésta es una opción peligrosa
           que hará que apt continúe sin preguntar incluso si se va a realizar algo
           potencialmente peligroso. No se debe usar excepto en situaciones muy especiales.
           ¡Utilizar force-yes puede destruir su sistema! Opción de configuración:
           APT::Get::force-yes.

```--reinstall```
           Reinstala los paquetes ya instalados, incluso si son la última versión disponible del
           paquete. Opción de configuración: APT::Get::ReInstall.

```--allow-unauthenticated```
           Ignora si los paquetes no se pueden autenticar, sin generar ningún diálogo sobre ello.
           Esto es útil para herramientas como pbuilder. Opción de configuración:
           APT::Get::AllowUnauthenticated.
<br>


# Syststem Information Commands 

```cat /proc/meminfo``` Shows details about your memory.

```cat /proc/partitions``` Shows the size and number of partitions on your SD card or hard drive.

```cat /proc/version``` Shows you which version of the Raspberry Pi you are using.

```df -h``` Shows information about the available disk space.

```df /``` Shows how much free disk space is available.

```dpkg - -get-selections | grep XXX``` Shows all of the installed packages that are related to XXX.

```dpkg - -get-selections``` Shows all of your installed packages.

```free``` Shows how much free memory is available.

```hostname -I``` Shows the IP address of your Raspberry Pi.

```lsusb``` Lists USB hardware connected to your Raspberry Pi.

```vcgencmd measure_temp``` Shows the temperature of the CPU.

```vcgencmd get_mem arm && vcgencmd get_mem gpu``` Shows the memory split between the CPU and GPU.

```find / -name example.txt``` Searches the whole system for the file example.txt and outputs a list of all directories that contain the file.

```poweroff``` To shutdown immediately.

```raspi-config``` Opens the configuration settings menu.

```shutdown -h now``` To shutdown immediately.

```shutdown -h 01:22``` To shutdown at 1:22 AM.

```cat example.txt``` Displays the contents of the file example.txt.

```iwlist wlan0 scan``` Prints a list of the currently available wireless networks.

```iwlist wlan0 scan | grep ESSID``` Use grep along with the name of a field to list only the fields you need (for example to just list the ESSIDs)

```ifconfig``` To check the status of the wireless connection you are using (to see if wlan0 has acquired an IP address).

```iwconfig``` To check which network the wireless adapter is using.
nmap: Scans your network and lists connected devices, port number, protocol, state (open or closed) operating system, MAC addresses, and other information.

```startx``` Opens the GUI (Graphical User Interface).

```ls -l``` Lists files in the current directory, along with file size, date modified, and permissions.

```scp user@10.0.0.32:/some/path/file.txt``` Copies a file over SSH. Can be used to download a file from a PC to the Raspberry Pi. user@10.0.0.32 is the username and local IP address of the PC, and /some/path/file.txt is the path and file name of the file on the PC.

```ls -la``` ver los permisos <br>
```df-h``` ver espacio de disco <br>
```du -hs``` ver espacio de folder<br>
```rm -r -f``` Borra directorio sin importar si esta vacio o no `rm -rf (directorio)`<br>
``` ~``` el simbolo (home) se hace con `Alg Gr + *`<br>
```&&``` Unir 2 comandos de consola<br>
```pwd``` directorio actual<br>

> :memo: **Note:** Abrir un archivo directamente desde el terminal de VScode. abrira una ventana nueva
```
code (filename.ext)
```

> :memo: **Note:** El ```&``` al final de un comando lo hace correr en segundo plano,(casi oculto), este no bloquea el sistema operativo si falla
> 
> :memo: **Note:** ```-y``` al final de un comando le dara YES a todas las preguntas impliucadas al comando

## Busqueda

Busca determinada palabra en un archivo:
```
cat <path archivo> | grep <Palabra_buscar>
```

<br>

# echo
echo "aaa" > va a borrar el contenido viejjo y va a sumar el nuevo <br>
echo "bbb" >> se va a sumar al final del archivo<br>
echo "zzz" <ruta del archivo> = echo "zzz" | sudo tee -a <ruta del archivo><br>

<br>

# On terminal
<p>Press <kbd>Ctrl</kbd> + <kbd>l</kbd> borrar terminal </p> 
<p>Press <kbd>Ctrl</kbd> + <kbd>shift</kbd> + <kbd>v</kbd> pega en el terminal desde el portapapeles </p> 

## Busqueda con filtro
```
cat <path file>| grep <word key>
```
<br>

# Use of wget
**How to Check if wgHet is Installed?** <br>
Most likely, the wget package is already on your system as it now comes pre-installed on most Linux distributions.
To check, open the terminal window and type in: ``` wget``` 

install: 
```
sudo apt-get install wget
``` 
<br>

# Cómo gestionar procesos

``` ps```  Muestra los procesos que se encuentran activos en el sistema actualmente.

``` ps -ef```  #mostrar todos los procesos

## Mostrar todos los procesos
``` top```  Muestra todos los procesos en funcionamiento <br>
``` htop```  Muestra todos los procesos en funcionamiento (version mejorado)
sudo apt-get install htop

## Cerrar un proceso
```kill PID```

## Forzar cierre de proceso por PID
```kill -9 PID```

## Gestionar procesos en el fondo
Cuando ejecutamos un comando o aplicación en la consola, esta se queda bloqueada hasta que el comando finaliza. Si queremos que la ejecución se realice en el fondo, añadimos la tecla ’&’ de esta forma

## Iniciar proceso en background
```comando &```

Si queremos poner un comando que ya se está ejecutando en background, podemos usar la combinación de teclas.

## Poner procesos en background
```control + z```
Si queremos visualizar los procesos que se ejecutan en segundo plano usamos el comando

## Mostrar procesos en background
```bg```
Y si queremos traer de vuelta el proceso más reciente puesto en segundo plano usamos,

## Traer al frente proceso
```fg```

<br>

## How to use wget to download files and interact with rest APIs
descagar archivo desde console
```sudo wget https://github.com/git/git/archive/v2.25.0.tar.gz -O git.tar.gz```

Usar el comando Wget para guardar archivos en el directorio especificado
```wget -P documents/archives/ https://wordpress.org/latest.zip```

Usar el comando Wget para descargas en segundo plano
```wget -b http://example.com/beefy-file.tar.gz```

Usando el comando Wget para descargar a través de FTP
```wget --ftp-user=YOUR_USERNAME --ftp-password=YOUR_PASSWORD ftp://example.com/something.tar```

Usando el comando Wget para continuar las descargas interrumpidas
```wget -c https://example/very-big-file.zip```

```‘--execute command’```
Execute command as if it were a part of .wgetrc (see Startup File). A command thus invoked will be executed after the commands in .wgetrc, thus taking precedence over them. If you need to specify more than one wgetrc command, use multiple instances of ‘-e’.

```‘--verbose’```
Turn on verbose output, with all the available data. The default output is verbose.

```‘--progress=type’```
Select the type of the progress indicator you wish to use. Legal indicators are “dot” and “bar”.

```‘--progress=bar’```

```‘--show-progress’```

> :memo: **Note:** Force wget to display the progress bar in any verbosity.
By default, wget only displays the progress bar in verbose mode.



wiki: https://www.digitalocean.com/community/tutorials/how-to-use-wget-to-download-files-and-interact-with-rest-apis

wiki : https://www.hostinger.es/tutoriales/usar-comando-wget/
	https://www.gnu.org/software/wget/manual/wget.html

<br>

## Sending GET requests

Wget lets you send GET requests by running a command that looks like the following:

``` wget -O- [ URL ]``` In the command above, the - after the -O option means standard output, so Wget will send the output of the URL to the terminal instead of sending it to a file as you did in the previous section. GET is the default HTTP method that Wget uses.
``` wget -O- -q https://jsonplaceholder.typicode.com/posts?_limit=2``` 

``` wget -O - http://dl.dropbox.com/u/11210438/flockonus-stack.sh | bash``` 

``` wget -q --show-progress https://code.jquery.com/jquery-3.6.0.min.js``` Wget lets you show the download progress bar but hide any other output by using the -q option alongside the --show-progress option.

**Non-Interactive Scripts**<br>
``` wget -O - http://website.com/my-script.sh | bash``` 
Note that when using this method, interactive scripts will not work.


**Interactive Scripts**<br>
In order to get interactive scripts working, you can use this:
``` bash <(wget -qO- http://website.com/my-script.sh)``` 

**Interactive Scripts that need to be run as root**<br>
Warning: This is extremely dangerous. Not recommended.
``` sudo su -c "bash <(wget -qO- http://website.com/my-script.sh)" root``` 

<br>

<p align="center"><img src="https://raw.githubusercontent.com/carjavi/rpi-linux-commands/master/img/linux-commands.png" height="200" alt=" " /></p>

# Modificación de permisos de ficheros en Linux

Para ver los permisos y propietarios de un archivo específico, puedes ejecutar este comando:
```
ls -l [nombre del archivo]
```
## El comando chmod
Para modificar los permisos, lo podemos hacer mediante los dos formatos:
```
chmod 744 [nombre del archivo]
```
```
chmod 755 /home/user 
```
Aquí hay una lista de los permisos más comunes para los archivos:
<p align="center"><img src="./img/permisos.png" width="800" alt=" " /></p>
<p align="center"><img src="https://raw.githubusercontent.com/carjavi/rpi-linux-commands/master/img/permiso_linux.png" height="800" alt=" " /></p>
Permisos comunes para directorios:
<p align="center"><img src="./img/permisos2.png" width="800" alt=" " /></p>

<br>

## Usar opciones con los comandos chmod y chown
```
chown -R 755 /etc/misarchivos
```
Después de introducir el comando anterior, el propietario puede leer, escribir y ejecutar todos los archivos y subdirectorios dentro del directorio /etc/misarchivos. El comando también da permisos de lectura y ejecución al grupo y a otros.
- -R (recursivo)
- -f o force. La línea de comandos ignorará cualquier error y aplicará los comandos chmod y chown.
- La opción -v (verbose) te da un diagnóstico de todos los archivos que son procesados por el comando.
- -c (changes) es imilar a -v, pero solo proporcionará información en caso de que los cambios se hayan realizado correctamente.



<br>
<br>

<p align="center"><img src="./img/linux cmd.jpg" width="800" alt=" " /></p>

<br>

---
Copyright &copy; 2022 [carjavi](https://github.com/carjavi). <br>
```www.instintodigital.net``` <br>
carjavi@hotmail.com <br>
<p align="center">
    <a href="https://instintodigital.net/" target="_blank"><img src="./img/developer.png" height="100" alt="www.instintodigital.net"></a>
</p>



