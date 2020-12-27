## postgre en GNU - Linux


Siempre debe iniciar sesión como usuario de Postgres para usar o realizar cualquier tipo de administración de PostgreSQL. De lo contrario, puede obtener errores de permisos y es posible que las cosas no funcionen como se esperaba.


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
sudo systemctl enable postgresql
```

<br/>

#### Ejecutar querys en la terminal

```
sudo -u postgres psql
```

<br/>

#### Mas informacion 
https://linuxhint.com/install-postgresql-10-arch-linux/
