# ### corse-service

* Responsable:  Santiago García (@Santi202305)  
* Repositorio base (.zip): https://github.com/Santi202305/Curse-Service.git  
* Docker Hub: santiago2305/corse_service-app:latest  
* Base URL (EC2): http://<ip-o-dominio>:8080  
* Swagger UI: http://<ip-o-dominio>:8080/swagger-ui  

---

### Entidades principales

#### curso

| Campo        | Tipo    | Restricciones |
|--------------|---------|---------------|
| id           | Long    | Autogenerado |
| nombre       | String  | No nulo, no vacío, 2–50 caracteres |
| descripcion  | String  | Máximo 255 caracteres |
| cupo         | Integer | No nulo, numérico, entre 1 y 500 |

---

### Endpoints principales

Controlador: `CursoRestController.java`  
Versión detectada: `/api/v1/cursos`

| Método | Ruta | Descripción |
|--------|-------|-------------|
| GET | /api/v1/cursos | Lista todos los cursos |
| GET | /api/v1/cursos/{id} | Busca un curso por ID |
| POST | /api/v1/cursos | Crea un nuevo curso |
| PUT | /api/v1/cursos/{id} | Actualiza un curso existente |
| DELETE | /api/v1/cursos/{id} | Elimina un curso por ID |

---

### Tecnologías

* Spring Boot (versión del proyecto en pom.xml)
* JDK 17+  
* Spring Web  
* Spring Data JPA  
* Validaciones básicas por anotaciones  
* SQL Script (`Curso-Serve.sql`)  
* Maven  
* Docker  
* Swagger 

---

### Características

* API REST funcional para gestión de cursos.
* Manejo de excepciones personalizado mediante `GlobalExceptionHandler`.
* Entidad Curso con atributos validados y mapeados con JPA.
* Script SQL incluido para carga inicial de datos.
* Configuración basada en `application.yml`.

---

## Responsables

| Rol                     | Nombre          | Usuario GitHub   | Observaciones |
|-------------------------|------------------|------------------|---------------|
| Autor del microservicio | Santiago García | @Santi202305 | Desarrollo de CRUD y clientes REST |
| DevOps                  | Santiago García | @Santi202305 | Dockerfile implementado |
---

Fecha: 2025-11-11

### Cambios relevantes

* Implementación completa del CRUD de Curso.
* Manejo de excepciones centralizado.
* Organización del proyecto en capas (delivery, domain, infraestructura HTTP).

---

