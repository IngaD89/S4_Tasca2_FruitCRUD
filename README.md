# Fruit Management API

Este es un proyecto de ejemplo para gestionar frutas usando una API RESTful construida con **Spring Boot**. La aplicación permite realizar operaciones CRUD (Crear, Leer, Actualizar y Eliminar) sobre frutas almacenadas en una base de datos H2.

## Tecnologías utilizadas

- **Java**
- **Spring Boot**
- **Spring Data JPA** para la persistencia de datos
- **H2 Database** (base de datos en memoria)
- **Maven** como gestor de dependencias

## Endpoints disponibles

La API permite realizar las siguientes operaciones:

### 1. Obtener todas las frutas

- **Método**: `GET`
- **Ruta**: `/fruits`
- **Descripción**: Obtiene una lista de todas las frutas en la base de datos.

### 2. Obtener una fruta por ID

- **Método**: `GET`
- **Ruta**: `/fruits/{id}`
- **Descripción**: Obtiene los detalles de una fruta específica por su ID.

### 3. Crear una nueva fruta

- **Método**: `POST`
- **Ruta**: `/fruits`
- **Descripción**: Crea una nueva fruta con los datos proporcionados en el cuerpo de la solicitud.

### 4. Actualizar una fruta existente

- **Método**: `PUT`
- **Ruta**: `/fruits/{id}`
- **Descripción**: Actualiza los detalles de una fruta existente por su ID.

### 5. Eliminar una fruta

- **Método**: `DELETE`
- **Ruta**: `/fruits/{id}`
- **Descripción**: Elimina una fruta existente de la base de datos por su ID.

## Excepciones y Gestión de Respuestas HTTP

La API utiliza **excepciones generalizadas** para manejar situaciones comunes y errores en las operaciones de la base de datos.

### Excepciones personalizadas

- **ResourceNotFoundException**: Se lanza cuando se intenta acceder a un recurso que no existe en la base de datos (por ejemplo, una fruta con un ID no válido).

La aplicación gestiona estas excepciones de manera centralizada, proporcionando respuestas adecuadas con el código de estado HTTP correspondiente.

### Respuestas HTTP con `ResponseEntity`

En cada operación, se utiliza **`ResponseEntity`** para estructurar la respuesta HTTP, lo que incluye tanto el cuerpo de la respuesta como el código de estado HTTP. Esto permite una mayor flexibilidad en la gestión de las respuestas, ya que podemos controlar la respuesta de manera más detallada según las necesidades de cada caso.

Por ejemplo:
- Si un recurso no se encuentra, se devuelve un **404 Not Found** con un mensaje adecuado.
- En el caso de éxito, se devuelve una **respuesta 200 OK** con los datos solicitados.

## Base de Datos H2

Este proyecto utiliza **H2** como base de datos en memoria, lo que permite que los datos se mantengan solo mientras la aplicación está en ejecución.


