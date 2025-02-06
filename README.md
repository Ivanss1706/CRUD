# API REST de Gestión de Usuarios con FastAPI y Pydantic (Ejemplo Básico)

Este código proporciona un ejemplo básico de una API REST para la gestión de usuarios utilizando FastAPI y Pydantic en Python.

## Configuración Inicial

* Se utiliza el framework FastAPI para crear la API REST.
* Se define un modelo de datos `User` con Pydantic, que incluye los siguientes campos (basados en datos de ejemplo del Titanic):
    * `PassengerId` (int): Identificador único del pasajero.
    * `Survived` (int): Indica si el pasajero sobrevivió (1) o no (0).
    * `Pclass` (int): Clase del billete (1, 2 o 3).
    * `Name` (str): Nombre del pasajero.
    * `Sex` (str): Sexo del pasajero.
    * `Age` (int): Edad del pasajero.

## Base de Datos Temporal

* Se utiliza una lista en memoria para almacenar los usuarios. **Importante:** Los datos se pierden al reiniciar el servidor.

## Endpoints Principales

* **`GET /usersclass/`**: Devuelve una lista con todos los usuarios.
* **`GET /usersclass/{id}`**: Busca un usuario por su `PassengerId` (Path parameter).
* **`POST /usersclass/`**: Crea un nuevo usuario. Se valida que el `PassengerId` no exista previamente.
* **`PUT /usersclass/`**: Actualiza un usuario existente.
* **`DELETE /usersclass/{id}`**: Elimina un usuario por su `PassengerId`.

## Funcionalidades Clave

* **Validación de Datos:** Pydantic realiza la validación automática de los datos de entrada según el modelo `User`.
* **CRUD Básico:** Implementación básica de las operaciones Create, Read, Update y Delete (Crear, Leer, Actualizar y Eliminar) para la gestión de usuarios.
* **Manejo de Errores:** Se incluyen manejos de errores sencillos para IDs no existentes.

## Uso Típico

* **Consultar todos los usuarios:** `GET http://localhost:8000/usersclass/`
* **Buscar usuario específico (Path parameter):** `GET http://localhost:8000/usersclass/5`
* **Crear usuario:** `POST http://localhost:8000/usersclass/` (con un cuerpo JSON que cumpla con el modelo `User`)
* **Actualizar usuario:** `PUT http://localhost:8000/usersclass/` (con un cuerpo JSON que cumpla con el modelo `User`)
* **Eliminar usuario:** `DELETE http://localhost:8000/usersclass/5`
