<p align="center"><img src="./img/Terminal.webp" height="200" alt=" " /></p>
<h1 align="center"> linux Commands</h1> 
<h4 align="right">February 24</h4>

<br>
<img src="https://img.shields.io/badge/OS-Linux%20GNU-yellowgreen">

<br>

# Commands Console
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

# On terminal
<p>Press <kbd>Ctrl</kbd> + <kbd>l</kbd> borrar terminal </p> 
<p>Press <kbd>Ctrl</kbd> + <kbd>shift</kbd> + <kbd>v</kbd> pega en el terminal desde el portapapeles </p> 

<br>

# SSH
### Setting SSH Ubuntu Server 20.04 

1. Create Folder <br>
Create the directory if required
```
sudo mkdir ~/.ssh
sudo nano ~/.ssh/authorized_keys
```

2. Permissions
```
chmod 700 ~/.ssh
chmod 600 ~/.ssh/authorized_keys
```

3. Verify Password Authentication
```
cat /etc/ssh/sshd_config | grep PasswordAuthentication
```
Debe decir "Yes". sino cambiar con el siguiente comando:

```
sudo nano /etc/ssh/sshd_config
```
Change ```PasswordAuthentication``` from no to ```Yes```. Save the file and restart the SSH service

4. Service ssh restart
```
sudo systemctl restart ssh
```

<br>

## Troubleshooting SSH UBUNTU 20.4

### SSH Permission Denied (publickey) 
probar si esta corriendo el servivio de SSH
```
sudo systemctl status sshd
```

ver la llave publica
```
cat ~/.ssh/id_rsa.pub
```

### Password Authentication
If public key authentication is not working, you can temporarily enable password authentication to troubleshoot further. Open the SSH configuration file on the remote server:
```
sudo nano /etc/ssh/sshd_config
```
Change ```PasswordAuthentication``` from no to ```Yes```. Save the file and restart the SSH service

```
sudo systemctl restart ssh
```

<br>


## How to Set Up SSH Key on Windows 10 
(with PowerShell / GitBash Terminal)

1. generate SSH keypair
```
ssh-keygen
```

2. Copying the Public Key to Your Ubuntu Server
```
ssh-copy-id username@server_ip
```
si hay error revisar Troubleshooting

 3. Authenticating to Your Ubuntu Server Using SSH Keys
```
ssh username@remote_host
```

<br>

> :bulb: **Tip:** Copying the Public Key to Your Ubuntu Server and create folder (one command)
```
cat ~/.ssh/id_rsa.pub | ssh username@remote_host "mkdir -p ~/.ssh && touch ~/.ssh/authorized_keys && chmod -R go= ~/.ssh && cat >> ~/.ssh/authorized_keys"
```


Creating and Using SSH Keys with GUI: https://www.purdue.edu/science/scienceit/ssh-keys-windows.html

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



