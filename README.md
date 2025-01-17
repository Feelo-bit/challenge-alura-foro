# Foro Alura Latam - Backend

Este repositorio contiene el backend del proyecto de foro desarrollado para el Challenge de Alura Latam. El backend ha sido construido utilizando **Java con Spring Boot** y sigue los principios de RESTful API para manejar las operaciones relacionadas con usuarios, topicos y respuestas.

---

## Tecnologías Utilizadas

- **Java 17**
- **Spring Boot** (2.7 o superior)
- **Spring Data JPA**
- **Hibernate**
- **MySQL**
- **Spring Security** (para autenticación y autorización)
- **Lombok**
- **Maven**

---

## Requisitos Previos

1. Tener instalado:
    - [Java 17](https://www.oracle.com/java/technologies/javase/jdk17-archive-downloads.html)
    - [Maven](https://maven.apache.org/install.html)
    - [MySQL](https://dev.mysql.com/downloads/installer/)
2. Un IDE como [IntelliJ IDEA](https://www.jetbrains.com/idea/) o Eclipse.

3. Configurar las credenciales de la base de datos en el archivo `application.properties` o `application.yml`.

```properties
# Configuración de la base de datos
spring.datasource.url=jdbc:mysql://localhost:3306/foro_alura_api
spring.datasource.username=tu_usuario
spring.datasource.password=tu_contraseña
```

---

## Estructura del Proyecto

El proyecto sigue una estructura modular para una mayor organización y mantenimiento:

- **Controller**: Contiene los endpoints de la API.
- **Service**: Lógica de negocio.
- **Repository**: Interacción con la base de datos.
- **Model**: Entidades del modelo de datos.
- **DTO**: Objetos de transferencia de datos entre capas.

---

## Endpoints Principales

### Usuarios
- **POST** `/api/usuarios` - Registrar un nuevo usuario.
- **GET** `/api/usuarios/{id}` - Obtener información de un usuario.
- **PUT** `/api/usuarios/{id}` - Actualizar información de un usuario.
- **DELETE** `/api/usuarios/{id}` - Eliminar un usuario.

### Tópicos
- **POST** `/api/topicos` - Crear un nuevo tópicos.
- **GET** `/api/topicos` - Listar todos los tópicos.
- **GET** `/api/topicos/{id}` - Obtener detalles de un tópico específico.
- **PUT** `/api/topicos/{id}` - Actualizar un tópico existente.
- **DELETE** `/api/topicos/{id}` - Eliminar un tópico.

### Respuestas
- **POST** `/api/Respuestas` - Agregar una respuesta a una publicación.
- **GET** `/api/Respuestas/{id}` - Obtener una respuesta específica.
- **DELETE** `/api/Respuestas/{id}` - Eliminar una respuesta.

---

## Seguridad

El backend utiliza **Spring Security** para manejar la autenticación y autorización:

- **JWT (JSON Web Tokens)** para el inicio de sesión.
- Roles de usuario: `ROLE_ADMIN` , `ROLE_MOD` y `ROLE_USER`.

Configura el header de autorización en cada solicitud:
```text
Authorization: Bearer <token>
```

---

## Pruebas

El proyecto incluye pruebas unitarias para los servicios y pruebas de integración para los endpoints. Ejecuta las pruebas con:
```bash
mvn test
```

