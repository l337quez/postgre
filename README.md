## postgre en GNU - Linux


Siempre debe iniciar sesión como usuario de Postgres para usar o realizar cualquier tipo de administración de PostgreSQL. De lo contrario, puede obtener errores de permisos y es posible que las cosas no funcionen como se esperaba.

#### Configuracion Inicial
Debemos hacer como usuario root 
```
sudo su - postgres
```

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

#### Cambiar clave del usuario para postgresql

```
sudo -u postgres psql -c "\password"
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

### Eliminar una base de Datos
En pgAdmin hacemos click derecho en la base de datos y clickiamos drop/delete

<br/>

##### Entramos a postgres por terminal
Si queremos crear la tabla desde la terminal
```
sudo -u postgres -i
```
creamos la tabla

<br/>

## Ver la Tabla
Si queremos ver la tabla asi como excell, debemos hacer click derecho en la tabla (ejm Precios) >> Script
>> Select script >> Tecleamos F5

<br/>

## Listar sesiones conectadas a la base de datos
Debemos cambiar nombre_db  y user_postgre por sus datos
```
psql nombre_db user_postgre
```
```
select * from pg_stat_activity where datname = 'mydatabasename';
```
<br/>

## Eliminar sesiones conectadas a la base de datos
Si tenemos alguna sesion abierta no podremos eliminar una base de datos, asi que procedemos a elimnar todas las conexiones.
Debemos cambiar nombre_db  y user_postgre por sus datos
```
psql nombre_db user_postgre
```

Escribimos nuestra clave, luego eliminamos todas las conexiones.
```
SELECT  * FROM pg_stat_activity WHERE datname='nombre_db';
```
luego salimos para poder eliminar manualmente la db en pgadmin
```
exit
```


<br/>


## Guardar una base de datos en un archivo .sql desde la terminal
```
pg_dump -U username -h localhost databasename >> sqlfile.sql
```


<br/>

## Restaurar una base de datos en un archivo .sql desde la terminal

```
pg_restore -i -h localhost -p 5432 -U postgres -d mibase -v "/home/damian/backups/mibase.backup"
```

<br/>

#### Mas informacion 
excelente informacion aqui : https://www.arteco-consulting.com/gestion-de-usuarios-en-postgresql/
https://linuxhint.com/install-postgresql-10-arch-linux/

https://wiki.archlinux.org/index.php/PostgreSQL

https://www.digitalocean.com/community/tutorials/how-to-install-configure-pgadmin4-server-mode-es
