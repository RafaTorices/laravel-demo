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

## Despliegue en local

> **Nota:**
>   
>   Modificar el archivo .env-example con los datos de conexión a la base de datos.
>

Para desplegar la aplicación en local, ejecuta el siguiente comando:

    docker-compose up -d
    
>
> **Nota:**
>    Lanzar el comando para realizar las migraciones de la base de datos:
>
>    docker-compose exec web php artisan migrate --force
>

Desplegará la aplicación en el puerto 8080 de tu máquina local.
Para acceder a la aplicación, abre un navegador y accede a la URL `http://localhost:8080`.