# Configuración de PostgreSQL y Adminer con Docker Compose

Este README proporciona instrucciones para configurar y ejecutar un contenedor de PostgreSQL junto con Adminer utilizando Docker Compose. PostgreSQL es una base de datos relacional de código abierto, y Adminer es una herramienta de administración de bases de datos web.

## Configuración en Docker Compose

El archivo `docker-compose.yml` define dos servicios: `postgreSQL` y `adminer`, y establece su configuración.

#### Servicio `postgreSQL`

- **Imagen:** Utiliza la imagen más reciente de PostgreSQL (`postgres:latest`).
- **Variables de entorno:** Establece las siguientes variables de entorno:
  - `POSTGRES_PASSWORD`: Contraseña de la base de datos (necesaria).
  - `POSTGRES_USER`: Usuario de la base de datos (por defecto, se utiliza "postgres" si no se especifica).
  - `POSTGRES_DB`: Nombre de la base de datos (se establece en "marcosfa").
- **Nombre del contenedor:** Se asigna el nombre "postgres_marcosfa".
- **Puertos mapeados:** Mapea el puerto 5434 del host al puerto 5434 del contenedor PostgreSQL.

#### Servicio `adminer`

- **Imagen:** Utiliza la imagen de Adminer (`adminer`).
- **Puertos mapeados:** Mapea el puerto 8080 del host al puerto 8080 del contenedor Adminer.
- Nota: Adminer es una herramienta de administración web para bases de datos, y se utiliza para interactuar con el servidor PostgreSQL.

## Ejecución en la Terminal

Para ejecutar estos servicios en Docker, sigue estos pasos en la terminal:

1. Asegúrate de que Docker Compose esté instalado en tu sistema.

2. Navega al directorio donde se encuentra tu archivo `docker-compose.yml`.

3. Ejecuta el siguiente comando para iniciar los contenedores en segundo plano:

   ```bash
   docker compose up -d
