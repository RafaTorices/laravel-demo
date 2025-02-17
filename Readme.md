# Proyecto demo Laravel App con Devops Tech
## Descripción
Este proyecto es una demo de una aplicación Laravel que se despliega:

    - En local con Docker y Docker Compose
    - En Cloud con AWS y Terraform

## Requisitos
Para poder ejecutar este proyecto necesitas tener instalado:

    - Docker
    - Docker Compose
    - Terraform
    - AWS CLI

## Despliegue en local con Docker
Para desplegar la aplicación en local, sigue los siguientes pasos:

- Se necesita una base de datos para la conexión de la aplicación. Se puede usar una base de datos MySQL o MariaDB.
- Modificar el archivo .env-example con los datos de conexión a la base de datos.
- Lanzar el comando:
    ```
    docker run -d --name app-laravel -p 8080:80 -v ./src:/var/www/html laravel-app
    ```
- Lanzar el comando para realizar las migraciones de la base de datos:  
    ```
    docker exec app-laravel php artisan migrate --force
    ```

## Despliegue en local con Docker-Compose
Para desplegar la aplicación en local, sigue los siguientes pasos:

- Modificar el archivo .env-example con los datos de conexión a la base de datos.
- Lanzar el docker-compose:
    ```
    docker-compose up -d
    ```
- Lanzar el comando para realizar las migraciones de la base de datos:  
    ```
    docker-compose exec app-laravel php artisan migrate --force
    ```

Se desplegará la aplicación en el puerto 8080 de tu máquina local.
Para acceder a la aplicación, abre un navegador y accede a la URL:
```
http://localhost:8080
```

