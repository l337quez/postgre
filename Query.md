### Conectarse a la base de datos
psql -h localhost -p 5432 -U name_user -d name_db


### Eliminar base de datos
drop database name_db;

### Crear Base de datos
create database name_db;

### Asignar usuario
alter database name_db owner to name_user;

### Eliminar
suponiendo que la tabla se llama users, solo va eliminar la data, la cabecera no la elimina.
```
SELECT * FROM users;
DELETE FROM users
```



</br>

### Hacer comentarios
Para hacer comentarios en una Query debemos usar / y *

```
/* SELECT * FROM users; */
```


