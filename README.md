## postgre en GNU - Linux


Siempre debe iniciar sesión como usuario de Postgres para usar o realizar cualquier tipo de administración de PostgreSQL. De lo contrario, puede obtener errores de permisos y es posible que las cosas no funcionen como se esperaba.


#### Iniciamos sesion 

```
sudo su - postgres
```

<br/>

#### inicializar el directorio de datos de PostgreSQL
directorio para GNU - Linux Arch

```
initdb --locale en_US.UTF-8 -D /var/lib/postgres/data
```

<br/>

#### Ejecutar querys en la terminal

```
sudo -u postgres psql
```

<br/>
