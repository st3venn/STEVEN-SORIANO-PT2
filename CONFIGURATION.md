# CONFIGURACIÓN CLOUD

Aqui, explicaré detalladamente la configuración de ownCloud una vez ya echa la instalación en la maquina virtual IsardVDI, como crear usuarios, asignando roles y permisos a cada uno de ellos y como administrar los archivos.

## 1. ACCESO A LA ADMINISTRACIÓN

- Una vez en [http://localhost](http://localhost), nos saldra esta pantalla:
![imagen46](https://drive.google.com/uc?export=view&id=1GrEJoVhLEEbhUlrEqxZQFr2LyFezYNRV)
En cada casilla, tienes que poner lo siguiente:

| Username | Password | Data folder         | Database user | Database password | Database name | Database host |
|----------|----------|---------------------|----------------|--------------------|----------------|----------------|
| usuario  | password | /var/www/html/data  | usuario        | password           | bbdd           | localhost      |

Recuerda que si has cambiado `usuario` y `password` tienes que poner los datos que has cambiado.
## 
- Ahora iniciamos sessión:
![imagen47](https://drive.google.com/uc?export=view&id=1gxQ6VLDJ4a8PZTb0uFyOP_Td4K4ziBtQ)

| Username or email | Password |
|-------------------|----------|
| usuario           | password |

## 2. CREACIÓN DE USUARIOS Y ASSIGNACIÓN DE GRUPOS

- Una vez ya dentro, nos vamos donde pone `usuario` y nos llevara a la siguiente pagina.
![imagen49](https://drive.google.com/uc?export=view&id=1z_OoCPTqEbjBsdOLfNmq8CmxaKlRQcZm)

![imagen50](https://drive.google.com/uc?export=view&id=1vqOH5j-JN4CfaPuoduNBasg75aaDYkdh)

## 
- Nos dirigimos a `Add group` y creamos 3 grupos: `admin`,`editor` y `visualizador`. `admin` ya esta creado por defecto.
![imagen50](https://drive.google.com/uc?export=view&id=1vqOH5j-JN4CfaPuoduNBasg75aaDYkdh)

![imagen51](https://drive.google.com/uc?export=view&id=1urJLrlduojlWq9YcCz5RyIzY1pqmAij-)

![imagen52](https://drive.google.com/uc?export=view&id=1IizlpPdmjiicroVBaGjwTAvnRR5Kt_CX)
##

- Creamos un minimo de 3 usuarios, con su correo electronico y al grupo donde quieres que pertenezca cada usuario. Una vez creado el usuario hacemos clic en `Create`.
   En mi caso he creado a:
  
| **Usuario ya viene predeterminado**                              |
|------------------------------------------------------------------|

| Usuario | Correo              | Grupo                          |
|---------|---------------------|--------------------------------|
| Juan    | juan@exemple.com    | Editor                         |
| Pepe    | pepe@exemple.com        | Visualizador                   |
| Hugo    | hugo@exemple.com        | Editor, Visualizador, Admin    |

![imagen53](https://drive.google.com/uc?export=view&id=1QxVXnFEHH2za7h1lVuLCT1mGb66Ec_AC)

![imagen54](https://drive.google.com/uc?export=view&id=1o_s2cW81bECxsgpLI7e4FseMxv3V0Scc)

![imagen55](https://drive.google.com/uc?export=view&id=1AjKVZ1NMxHLzbLQ4KKQgrKlx7Rj9LYj1)
## 

- Una vez creado, quedaria tal que asi:
![imagen56](https://drive.google.com/uc?export=view&id=1b7_9HasgBXdcBKVA7837W9-Kzj8vBKbO)
## 

## 3. ASSIGNACIÓN DE PERMISOS

- Hacemos clic en las 3 rayas del lateral izquierdo y nos vamos a `Files`, luego en el signo `+` creamos una nueva carpeta que se llame `permisos`
![imagen57](https://drive.google.com/uc?export=view&id=1SMGMSYaHFCxzzX2Uv-gxF6h3hK7tDMJv)
## 

- Vamos a la carpeta que hemos creado y luego a `sharing`
![imagen58](https://drive.google.com/uc?export=view&id=1w12-yap9iVcf9RpWCcnwRex5gfjbXIrL)
## 

- En `Sharing`, en el apartado `User and Groups` añadimos a los usuarios que hemos creado. En cada usuario nos vamos al signo de `ajustes` y le establemos los permisos a cada grupo.
![imagen59](https://drive.google.com/uc?export=view&id=1w12-yap9iVcf9RpWCcnwRex5gfjbXIrL)
## 

- Yo, he añadido a cada grupo los siguientes permisos:

| Grupo          | Permisos                              | 
|--------------|-------------------------------------|
| Admin        | can share, can edit, create, change, delete |
| Editor       | can edit, create, delete             |
| Visualizador | ningún permiso                       |

| ㅤㅤ       | ㅤㅤ           |
|--------------|-------------------|
| can share    | puede compartir   |
| can edit     | puede editar      |
| create       | crear             |
| change       | cambiar           |
| delete       | eliminar          |

![imagen60](https://drive.google.com/uc?export=view&id=1PkXSXEikeWB4Zq6KnnBG82mgNt9c7tWe)

![imagen61](https://drive.google.com/uc?export=view&id=1o6JjH1S9HpglaowfThKZTdepN1hn6oLA)

![imagen62](https://drive.google.com/uc?export=view&id=1z7sHBxMbANa-m7cf40vUO5Z-S05d5PT8)

![imagen63](https://drive.google.com/uc?export=view&id=1IefL7I96sQFN0Nyh96zwpDpRH95l3L8e)

![imagen64](https://drive.google.com/uc?export=view&id=1-insFeuKcn3sMA_2yc909Itox1-DNi7B)

![imagen65](https://drive.google.com/uc?export=view&id=19M9w3pIfZ-ZdaMjg9PHU6u2v2jzwm8Rc)

- En `Activities` ya saldra que esta compartido con cada grupo.
![imagen66](https://drive.google.com/uc?export=view&id=1cOAVPcbS4hNF6U1DgW8f0opGfO8tbDs5)

## 4.CREACIÓN DE CARPETAS

- En la misma pagina del apartado `All files`, hacemos clic al signo `+` y creamos **3 carpetas**. Yo he creado `Documentos`, `imagenes` y `proyectos`.
![imagen67](https://drive.google.com/uc?export=view&id=1W5P-qkFGCF9pZenMo_jbCRhatubJ-rXG)

![imagen68](https://drive.google.com/uc?export=view&id=1-p10xJfqAy236FX9oer072C8ArnojN56)

![imagen69](https://drive.google.com/uc?export=view&id=1EcI3zJtuy-6LSqSLN-DmcxNuofpNFW9x)

## 5. CARGA DE ARCHIVOS

- En el simbolo `+` nos aparecerà 3 opciones, le damos a `Upload`
![imagen70](https://drive.google.com/uc?export=view&id=18HVPlvhTDVvdekLv-2AsmDltA-4f2qe5)

- Seleccionamos el archivo que queremos subir y le damos a `abrir`. Nos mostrarà que lo esta subiendo y ya estaria subido.
![imagen71](https://drive.google.com/uc?export=view&id=11jHsPCOZr-5rxMfSrok2z-WWrXeXYwyV)
![imagen72](https://drive.google.com/uc?export=view&id=1bTGUAtjBSIDNU8Y9kpNqC3BwwIxtbMVt)

## 6. MOVER ARCHIVOS A CARPETAS

- Ya subido el archivo, lo selecionamos y lo movemos a la carpeta donde queremos que vaya. Yo lo he puesto en `Proyectos`.
![imagen73](https://drive.google.com/uc?export=view&id=1a6gAHbwRIMFVhqCXVUA3hDfa6OLVhGWT)

![imagen74](https://drive.google.com/uc?export=view&id=1qBoXkljQw-4p87pIxJJpospo0hmWjVen)

- Entramos en la carpeta y podemos ver como el archivo se ha movido a esa carpeta.
![imagen75](https://drive.google.com/uc?export=view&id=1NRXGW97JWwiUmVddI0-oKkI-hRcqOsl_)

## 7. ORDEN DE CARPETAS
- Es muy sencillo, en `Files`, nos dirigmos a la flecha que esta al lado de `Name` y hacemos clic.
![imagen 89](https://drive.google.com/uc?export=view&id=1oZZ0OXPHp_3ccLkGgCdYfojGxfW1zl7-)

- Y ya estaria ordenado alfabeticamente.
![imagen 90](https://drive.google.com/uc?export=view&id=1zGxLfEcveB-yfafKvb4nJWSjLtMIRvbd)

## 8. COMPARTICIÓN DE ARCHIVOS/CARPETAS

- Seleccionamos la carpeta o archivo que queremos compartir y nos vamos al simbolo de `compartir`. En este caso utilizare la carpeta `Proyectos` porque ahi dentro puse el fichero.
![imagen76](https://drive.google.com/uc?export=view&id=1I0g8G99HNSzNA1jhJlnFbdZlYFSLpi-v)

- En el apartado de `Sharing` ponemos en el buscador el nombre del usuario a cual le queremos compartir la carpeta.
![imagen77](https://drive.google.com/uc?export=view&id=1LEPBPrzJwQn6fvkHq88s7rr0wkFca-sP)

- Y ya estaria compartida la carpeta con el usuario.
![imagen78](https://drive.google.com/uc?export=view&id=1VhLcyjAkvQlUnTPEVctYyGjtE9SG-t97)

- Le assignamos los roles que quiere que tenga el usuario.
![imagen79](https://drive.google.com/uc?export=view&id=18cC4snsFG2ldfivr5K0v3uJ6yfWVf0uM)

## 9. POLITICAS DE SEGURIDAD

- Nos dirigimos a `Setings`.
![imagen80](https://drive.google.com/uc?export=view&id=1B_DaURTM4y8u02Q8fTR0FHUeXaOsv2-q)

- En `Settings` vamos al apartado `Admin` y luego a `Sharing`
![imagen81](https://drive.google.com/uc?export=view&id=1ASXEKaihq4dTnQLjEQqrbL-NUpr2Ww5p)

- Activamos `Set default expiration date` y le ponemos unos dias determinados, pasados esos dias se expirarà el compartido.
![imagen82](https://drive.google.com/uc?export=view&id=1ns7uGvrHAU8FBNpQcGfGWSxXkEk0IsJZ)

- Ahora activamos `Restrict user to only share with users in their groups`, para que el usuario no pueda compartir a otros usuarios que no esten autorizados.
![imagen 83](https://drive.google.com/uc?export=view&id=1XRoQRgCfstMQ-DChssfjr7UH6OBCDqSo)

- Finalmente, activamos `Enforce password protection for ready-only links` para que los usuario solo puedan leer lo compartido, asi no lo pueden editar.
![imagen 84](https://drive.google.com/uc?export=view&id=1TxdXD8TIblyfIvOu4unaBUNIqMiIhe_t)

- Ahora, nos vamos a `Files` y escogemos una carpeta, una vez ahi, hacemos clic al simbolo de `compartir`.
![imagen 85](https://drive.google.com/uc?export=view&id=1wOvHrrkvVw1FFMORvZVm5fUnK1CGlK8p)

- En el apartado de `Sharing`, nos vamos a `Public links` y hacemos click en `Create public link`.
![imagen 86](https://drive.google.com/uc?export=view&id=10GQTgiWFEqArNuxAov_XIv3G8MHnCHIM)

- Se abrira un pequeño menú, en el apartado `Password` añadimos una contraseña y hacemos clic en `Share`.
![imagen 87](https://drive.google.com/uc?export=view&id=1A0ivplqRydCaGUTEr2VALDQeWu9NVeBK)

- Y ya saldria el simbolo de **enlace** en el dibujo de la carpeta.
![imagen 88](https://drive.google.com/uc?export=view&id=1NeHS_gWzMsF0Pp2GoeD6-PwlRF3XtaUB)

## 10. ACCESO REMOTO EN OTRA MAQUINA.

- Cerramos la maquina virtual por completo.
![imagen 91](https://drive.google.com/uc?export=view&id=1yaT8VU5VbTGfBUOkrrAB85RhP6D9PMcy)

- Una vez cerrada, nos vamos a los **3 puntos** y al simbolo del **lapiz**.
![imagen 92](https://drive.google.com/uc?export=view&id=1rU3FkEdll7YpGxraMNoyzA6bpYt1xV8O)

![imagen 93](https://drive.google.com/uc?export=view&id=1_nEh_qW2BdmO8IEmMHLT4yz8W41Yd1Qc)

- En el apartado `Xarxes` ponemos la red `Puigcastellar1`, y le damos clic en `Envia`.
![imagen 94](https://drive.google.com/uc?export=view&id=1MD1eX6LZV1j7GrJbNOcTsBiqP5aZqKzt)
![imagen 95](https://drive.google.com/uc?export=view&id=1k42tg9cfqLKPNJw1ki75cUsw2tYZ6LQS)

- Volvemos abrir la maquina virtual.
![imagen 96](https://drive.google.com/uc?export=view&id=1AwkoxCWu3aJ-D67zD7czA4idihbEjtyR)

- Ahora con el comando:
```bash
ip a
```
Vemos la IP de la red.
![imagen 97](https://drive.google.com/uc?export=view&id=1U5gHeaENqyhFFJkxyfGf3ZDn8iT_ruy1)

- Luego desde la maquina local, volvemos a realizar el mismo comando para ver si esta la misma `IP que la maquina virtual`. Como no salia la misma `dirección IP` comprobamos hacer ping con la `IP` de la maquina virtual.
![imagen 98](https://drive.google.com/uc?export=view&id=1bYFBJwQlU8Mvmfgn6kqdVt2g3u8Rk3Ow)

- Como el ping si funciona, abrimos el archivo donde esta la configuración.
  
- Primero entramos al directorio `/var/www/html`.
```bash
cd /var/www/html
```
![image](https://github.com/user-attachments/assets/26ea6265-bd2b-4f5f-ae24-acc91ceedbb2)

- Una vez en el directorio, verificamos si `apache 2` esta activo con el comando:
```bash
sudo systemctl restart apache2
```
![image](https://github.com/user-attachments/assets/c8394e06-9e4f-4171-a1b2-0e4ed8608741)

- En el apartado de `trusted_domains`, tiene que salir `0=> 'localhost'`, debajo de ello, pondremos `1=> '192.168.0.0'` según la **IP** que te haya tocado.
![image](https://github.com/user-attachments/assets/95506e31-2df2-40fc-80a7-668afbe5d8bf)

- En mi caso puse `1=>'192.168.236.151'`.
![imagen 99](https://drive.google.com/uc?export=view&id=1E3JRZUA728yaqHs2hVPSxqXNyQzTWOKz)

- Una vez echo lo anterior, nos dirigmos al navegador de la maquina local y ponemos `http://192.168.236.151`.
![imagen 100](https://drive.google.com/uc?export=view&id=1vai_wuzXnG_e5aXgOn12_6_2L6JIQar-)

Y finalmente puedes acceder a ownCloud desde la maquina local.



















































