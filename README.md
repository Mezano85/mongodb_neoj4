# Metodos de Captura y Almacenamiento de los Datos

---

| Concepto    | Descripción                         |
|-------------|-------------------------------------|
| Universidad | Unir                                |
| Profesor    | Abel Alejandro Coronado Iruegas     |
| Alumno      | Francisco García Mezano             |
| Inicio      | 19 de Febrero 2024                 |

## Objetivo
---
El precente repositorio contiene el material funciona con docker para levantar un servicio de Jupyter, Mongo y Neoj4 con el objetivo de realizar la actividad grupal 2 de Metodos de Captura y Almacenamiento de datos.

## Formato de Directorios
---

* **docker_files**: Contiene los archivos de configuración necesarios para poder replicar los ejercicios de las actividades.

* **databases**: Dentro de esta carpeta se encuentran los datos de las bases de datos levantadas con el servicio, esto con la finalidad de persistir la información cargada en las bases de datos, ademas, dentro de la carpeta de la base de datos se encuentra **un ejemplo de conexion a la misma desde un jupyer notebook**.  Dentro del databases se encuentra el directorio import para el ejercicio neo4j donde deberán ponerse los archivos para importar datos a esta base de datos.

## Docker Compose
---

Para levantar el ambiente local se ejecutan las siguiente sentencia:

```
docker-compose -f docker_files/docker-compose.yml up --build -d
```

Para detener el ambiente:
```
docker-compose -f docker_files/docker-compose.yml down
```

Para limpiar los contenedores:
```
docker system prune
```

## Acceso a Servicios
---

* Jupyter -> [http://localhost:8888](http://localhost:8888)
* Mongo-Express -> [http://localhost:8081](http://localhost:8081)
* Consola de Neo4j -> [http://localhost:7474](http://localhost:7474)


## Acceso al contenedor de Mongo
---

Para acceder directamente al contenedor de Mongo desde la terminal.

```
docker exec -it mongodb bash
``` 

Dentro del contenedor se puede ejecutar los monitores correspondientes:
```
mongostat --discover --authenticationDatabase=admin -u root
```
```
mongotop 5 --authenticationDatabase=admin -u root
``` 

Para ambos comandos se solicitará el password que por default en este proyecto es **mongo**  y puede ser modificado desde el archivo **.env**
