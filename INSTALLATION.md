# INSTALACIÓN OWNCLOUD

Aquí explico cómo he instalado ownCloud en la máquina virtual de IsardVDI. Primero he preparado el sistema con Ubuntu, luego he instalado los programas necesarios como Apache, MySQL y PHP. Después he descargado ownCloud y lo he configurado para que funcione bien desde el navegador. Aquí enseño todos los pasos que he seguido.

## 1. Configuración IsardVDI

- En el navegador buscamos [IsardVDI](https://elmeuescriptori.gestioeducativa.gencat.cat/), una vez en la página, creamos una nueva máquina en `Escriptori nou`.

  ![IsardVDI paso 1](https://drive.google.com/uc?export=view&id=1lFn-wQmq7rqh1_sMo9O0ccm0dYJTpeig)

- Le ponemos el nombre que queremos como se llame nuestra máquina y seleccionamos la plantilla de `ubuntu-24.04-desktop`, es la que usamos normalmente al crear máquinas virtuales. Finalmente hacemos clic en `crea`.

  ![IsardVDI paso 2](https://drive.google.com/uc?export=view&id=1qsurYbteoabKQyKYN8z4BawRTDTsHP_z)

- Una vez creada la máquina, en los **3 puntos** nos saldrá el signo de un lápiz, clicamos y nos llevará a la configuración de la máquina.

![imagen3](https://drive.google.com/uc?id=1xWET3Qgt3ID73I6Bqg_ceoEhSYQL1YCC)

- Ahora, en la edición de la máquina virtual, nos dirigimos al apartado hardware y editamos `vCPUS`, `Memoria (GB)` y `Video`.

![imagen4](https://drive.google.com/uc?id=1YAgJ2-MptMahOuStUtq5pPaaas_XaL6l)
He puesto 20 GB de memoria. Lo demás lo he dejado predeterminado.

- Iniciamos la máquina una vez todo esté hecho.

![imagen5](https://drive.google.com/uc?id=1yaT8VU5VbTGfBUOkrrAB85RhP6D9PMcy)

## 2. INSTALACIÓN OWNCLOUD

Una vez creada la máquina virtual, empezamos a usar la terminal para instalar y configurar ownCloud. A continuación, se muestran los comandos paso a paso:

Primero descargamos el `.zip` de ownCloud y le cambiamos el nombre.

[Descargar ownCloud](https://download.owncloud.com/server/stable/owncloud-complete-20240724.zip)
![imagenFICHERO](https://drive.google.com/uc?export=view&id=1QQKW656DEQckMXGriP4dX_92vVKFv1qD)
Yo he puesto ese nombre, pero tu lo puedes poner como quieras, solo que recuerda el nombre cambiado.

- Abrimos la terminal:

![imagen7](https://drive.google.com/uc?id=1OakKsgq2v1pcux-0wyJ-Gh75d2IlSdKu)

Las siguientes comandas son para poder instalar la versión 7.4 PHP en nuestro sistema.
- con:
 ```bash
sudo apt install software-properties-common -y
```
Instalamos los requisitos previos de PPA (Personal package archive).

![imagen8](https://drive.google.com/uc?export=view&id=1TOaGUCSUPDJ-7ia_p0i-rNqE7wgCjIB9)

- Instalamos las herramientas para poder trabajar en los archivos PPA con: 
```bash
LC_ALL=C.UTF-8 sudo add-apt-repository ppa:ondrej/php -y
```
![imagen9](https://drive.google.com/uc?export=view&id=1R4WhxYjJGGHBGrIyXkMsDypMaPhKoOWv)

- Actualizamos los repositorios con:
```bash
sudo apt update
```
![image](https://github.com/user-attachments/assets/2d162a27-1844-455f-bb09-725b7664a459)

- Instalamos las librerías PHP con los siguientes comandos: 
```bash
sudo apt install php7.4 -y
```
![imagen11](https://drive.google.com/uc?export=view&id=1vf6EsQ58FMoiDgUTnlmANUbcEUT0TYIn)

![imagen12](https://drive.google.com/uc?export=view&id=1Bwsk9CbzzY71p3ZUxSD61hA-UDD_lmsq)
La mayoría de pasos tendrás que esperar unos minutos para que el progreso se descargue correctamente.

```bash
sudo apt install -y php libapache2-mod-php7.4
```
![imagen13](https://drive.google.com/uc?export=view&id=1mc-q5fTgXBUvV5RojoIkZrS436cOLRhw)

```bash
sudo apt install -y php7.4-fpm php7.4-common php7.4-mbstring php7.4-xmlrpc php7.4-soap php7.4-gd php7.4-xml php7.4-intl php7.4-mysql php7.4-cli php7.4-ldap php7.4-zip php7.4-curl
```
![imagen14](https://drive.google.com/uc?export=view&id=12N-Dv0ty8ybfXmnLnMGrlEWPho7rFoMP)

- Con este comando:
```bash
sudo update-alternatives --config php
```
Seleccionamos la versión de PHP que queramos, en mi caso he dejado la que está predeterminada, pero podéis coger la adecuada para vosotros.
![imagen15](https://drive.google.com/uc?export=view&id=1qg9AKrynBOzO1XUD_kNgv0N2ngn_nInU)

- Ahora activamos los módulos de `apache2`.
```bash
sudo a2enmod proxy_fcgi setenvif
```
![imagen16](https://drive.google.com/uc?export=view&id=1bjw0W3qicAaJ4Xc7ATIVBIHxUq85kyCK)

```bash
sudo a2enconf php7.4-fpm
```
![imagen17](https://drive.google.com/uc?export=view&id=18yueyZT0IlbSRCFzSAKVdZ8admySzTe6)

- Finalmente, reiniciamos **apache2**.
```bash
sudo service apache2 restart
```
![imagen18](https://drive.google.com/uc?export=view&id=1pljYToFPYHNDvBF2fOcbNP1fdmWfEhz3)

### Ahora estos comandos son para ya poder instalar todo correctamente y llegar a la configuración del ownCloud.
Como dije anteriormente, la mayoria de comandos tienen que descargar progreso y hay que esperar unos minutos, tambien al ejecutar algunos comandos, se empieza a realizar muchos datos que no caben en la pantalla, esta demostrado en algunas capturas para que lo podais ver.

- Actualizamos la maquina con lo siguiente:
```bash
sudo apt update
```
![imagen19](https://drive.google.com/uc?export=view&id=1rs9SRdTCtJwA7ZxM9Dn4lPPKwl1noQg9)

```bash
sudo apt upgrade
```
![imagen20](https://drive.google.com/uc?export=view&id=1hkx_clQU9-Zfs7tDgq5asa7kdASHbJSo)
![imagen21](https://drive.google.com/uc?export=view&id=1bxx6PbdelVlufO0a_rWfruiIYvB1diO7)


- Instalamos el servidor web de **Apache2** con el siguiente comando:
```bash
sudo apt install -y apache2
```
![imagen22](https://drive.google.com/uc?export=view&id=1ahOlteOuUlq5dAnijOlsG2ZeXoLRTj-v)

- Instalamos el servidor de la base de datos con:
```bash
sudo apt install -y mysql-server
```
![imagen23](https://drive.google.com/uc?export=view&id=1E3iJ2MUCjPYLWJqNiRbo47r3b6-0ooq-)
![imagen24](https://drive.google.com/uc?export=view&id=1S-BgSbL4bK0PZXc-oUyZDTxqb-I3wL1s)


- Ahora con estos 2 comandos, instalaremos algunas librerias `php`, porque las aplicaciones la usan como lenguaje principal.
```bash
sudo apt install -y php libapache2-mod-php
```
![imagen25](https://drive.google.com/uc?export=view&id=1llf55_BEZKxMmf3nGzrt2edm88nM6Fi4)

```bash
sudo apt install -y php-fpm php-common php-mbstring php-xmlrpc php-soap php-gd php-xml php-intl php-mysql php-cli php-ldap php-zip php-curl
```
![imagen26](https://drive.google.com/uc?export=view&id=105i5KA8EbKnczzslXujzDEitCA2SLM8o)

- Finalmente reiniciamos **Apache2**
```bash
sudo systemctl restart apache2
```
![imagen27](https://drive.google.com/uc?export=view&id=1D7NoPMbhKYSEU7QAAVBnFM8H3yqYgRN4)


### Ahora vamos a configurar el MySQL.
- Accedemos a la consola de MySQL con:
```bash
sudo mysql
```
![imagen28](https://drive.google.com/uc?export=view&id=1GJOzKH9wIL3MwXNABDMgu-LeCpld6828)

- Ahora dentro de la consola, creamos la base de datos con:
```bash
CREATE DATABASE bbdd;
```
![imagen29](https://drive.google.com/uc?export=view&id=1l9jcpKJ0-45mHw3O_gxg2KnFG1gHg1RK)

- Creamos el usuario que se mostrara en ownCloud y le damos privilegios:
```bash
CREATE USER 'usuario'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password';
```
Puedes cambiar `usuario` por tu nombre real o tu apodo, pero ten en cuenta que todo lo tendras que poner con el nuevo nombre.
![imagen30](https://drive.google.com/uc?export=view&id=1Ly8FmY90tIoNrlZbE8qjUEi4inZ5zVbn)
```bash
GRANT ALL ON bbdd.* to 'usuario'@'localhost';
```
![imagen31](https://drive.google.com/uc?export=view&id=1LBPqIvB86li-pGmt5JZls47KZUM0dzlw)

- Y finalmente salimos de la base de datos.
```bash
exit
```
![imagen44](https://drive.google.com/uc?export=view&id=1Hua14er0XF-9yAY9bT1HJ8qGx83nD1l2)

- Ahora con:
```bash
mysql -u usuario -p
```
probamos la conexión con la base de datos.
![imagen32](https://drive.google.com/uc?export=view&id=1R1j1n1s_6pRTWQ4P1YDO_SzAJGF3kDcI)

- Ahora descargaremos los ficheros con los siguientes comandos:
```bash
sudo cp ~/Descargas/app-web.zip /var/www/html
```
![imagen33](https://drive.google.com/uc?export=view&id=1PmZnFYU_Bkg9ZLR8K0BXRkOrgPprTZbG)
En mi caso, como tengo el sistema en Español, pongo `Descargas`, que es donde tengo guardado el fichero, si has cambiado el nombre del fichero tambien lo deberias cambiar en este comando.

- Nos dirigmos al directorio `/var/www/html` con:
```bash
cd /var/www/html
```
![imagen35](https://drive.google.com/uc?export=view&id=1kmDXqZR0M6OLyEsxvjGHW3hlmVhJQgMl)

- Una vez dentro del directorio `/var/www/html` descomprimimos el fichero con el siguiente comando:
```bash
sudo unzip app-web.zip
```
![imagen36](https://drive.google.com/uc?export=view&id=1gkTt7NJhjRIzD9T0bwCIitvBNQqMehiX)
![imagen37](https://drive.google.com/uc?export=view&id=1V8eydB7sEAjgU3S_AmF0x3FMQnTQQQ_B)

- Ahora con:
```bash
ls /var/www/html
```
Podemos mirar que nombre se ha puesto despues de descomprimir el fichero.
![imagen38](https://drive.google.com/uc?export=view&id=111B4aNXrSDIUp5v7q5ys34vR1a1gDs1u)

- Una vez mirado el nuevo nombre (en mi caso **owncloud**), podemos copiar todos los ficheros al directorio `/var/www/html` con:
```bash
sudo cp -R owncloud/. /var/www/html
```
![imagen39](https://drive.google.com/uc?export=view&id=1XON6lkjgiTOTqJUmuhUHaJFl-jmwMnl2)

- Una vez hecho el `unzip`, eliminamos la carpeta que hemos creado:
```bash
sudo rm -rf owncloud/
```
![imagen40](https://drive.google.com/uc?export=view&id=1U-CWme2jSBcVxCr9hs9c4igTs8FbI9PW)

- Ahora nos salimos del directorio con `cd` y eliminamos el fichero `index.html` con:
```bash
sudo rm -rf /var/www/html/index.html
```
![image](https://github.com/user-attachments/assets/b5173746-4e58-4844-806e-84680ace0c21)

- Ahora aplicamos permisos al directorio `/var/www/html` con los siguientes comandos:
```bash
cd /var/www/html
```
```bash
sudo chmod -R 775 .
```
![imagen41](https://drive.google.com/uc?export=view&id=1TXKfQM-7FRS7YoGzwNavfX51VhzQ1E2Z)
```bash
sudo chown -R usuario:www-data .
```
![imagen42](https://drive.google.com/uc?export=view&id=1LPeFLOkPDagZZyZEkxDNQN_oOG7L4bN5)

## 3. ACCEDER AL NAVEGADOR PARA VERIFICAR

Abrimos el navegador y en el buscador ponemos [http://localhost ](http://localhost) 
![imagen43](https://drive.google.com/uc?export=view&id=1LIHGd0oFHmFxtIxNxSffwrbSj7xTEPOD)

Ahora, si todo ha ido bien tiene que salir la pagina de ownCloud y se iniciaria la configuración.

Para ver la configuración de `ownCloud` dirigete al otro repositorio.
[Configuración ownCloud](CONFIGURATION.md)










