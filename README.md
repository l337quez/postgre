## postgre en GNU - Linux


Siempre debe iniciar sesión como usuario de Postgres para usar o realizar cualquier tipo de administración de PostgreSQL. De lo contrario, puede obtener errores de permisos y es posible que las cosas no funcionen como se esperaba.

#### Configuracion Inicial
Antes de que PostgreSQL pueda funcionar correctamente, se debe inicializar el clúster de la base de datos: 
```
initdb -D /var/lib/postgres/data
```

<br/>

#### Conocer el usuario que estas usando para postgresql

```
sudo -l postgres
```

<br/>

#### Iniciamos sesion 

```
sudo su - postgres
```

<br/>

#### inicializar el directorio de datos de PostgreSQL
directorio para GNU - Linux Arch. Yo vivo en Venezela, asi que mi configuracion local es es_VE.UTF-8

```
initdb --locale es_VE.UTF-8 -D /var/lib/postgres/data
```

Si todo salio bien, entonces deberia salir algo como esto..
Completado. Ahora puede iniciar el servidor de bases de datos usando:

    pg_ctl -D /var/lib/postgres/data -l archivo_de_registro start

<br/>

#### Cerramos sesion 

```
exit
```

<br/>

#### Corremos el Demonio de Posgres 

```
sudo systemctl start postgresql
```

<br/>

#### Ver el status del Demonio

```
sudo systemctl status postgresql
```

<br/>

#### Mantener corriendo el Demonio

```
sudo systemctl enable postgresql.service
```

<br/>

#### Ejecutar querys en la terminal

```
sudo -u postgres psql
```

Si te da error de permisologia ejecuta el comando asi
```
sudo -i -u postgres psql
```

<br/>

### Crear una base de Datos
creamos la tabla con pgAdmin.
Hacemos click derecho y creamos un servidor.


 ![alt text](https://assets.digitalocean.com/articles/pgadmin/create_server_box_resized.png)

<br/>

Le pondemos cualquier nombre

 ![alt text](https://assets.digitalocean.com/articles/pgadmin/server_general_tab_resized.png)

<br/>

Configuramos el sevidor

 ![alt text](https://assets.digitalocean.com/articles/pgadmin/connection_tab_resized.png)


<br/>

##### Entramos a postgres por terminal
Si queremos crear la tabla desde la terminal
```
sudo -u postgres -i
```
creamos la tabla

<br/>

#### Mas informacion 
https://linuxhint.com/install-postgresql-10-arch-linux/

https://wiki.archlinux.org/index.php/PostgreSQL

https://www.digitalocean.com/community/tutorials/how-to-install-configure-pgadmin4-server-mode-es
