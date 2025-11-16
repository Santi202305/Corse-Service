# ### corse-service

* Responsable:  Santiago García (@Santi202305)  
* Repositorio base (.zip): https://github.com/Santi202305/Curse-Service.git  
* Docker Hub: (pendiente integración)  
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
| semestreId   | Long    | No nulo |
| docenteId    | Long    | No nulo |

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

### Integraciones externas

#### semestre-service  
Cliente: `SemestreClient.java`

| Método | Ruta | Descripción |
|--------|------|-------------|
| GET | /semestres/{id} | Obtiene datos del semestre por ID |

Objeto recibido: `SemestreDTO`  
Campos detectados:  
- id  
- nombre  
- descripcion  

---

#### docente-service  
Cliente: `DocenteClient.java`

| Método | Ruta | Descripción |
|--------|------|-------------|
| GET | /docentes/{id} | Obtiene datos del docente por ID |

Objeto recibido: `DocenteDTO`  
Campos detectados:  
- id  
- nombre  
- apellido  
- correo  

---

### Tecnologías

* Spring Boot (versión del proyecto en pom.xml)
* JDK 17+  
* Spring Web  
* Spring Data JPA  
* Validaciones básicas por anotaciones  
* SQL Script (`Curso-Serve.sql`)  
* Maven  
* Docker (pendiente integración)  
* Swagger (pendiente integración)

---

### Características

* API REST funcional para gestión de cursos.
* Integración vía REST con Semestre-Service y Docente-Service.
* Manejo de excepciones personalizado mediante `GlobalExceptionHandler`.
* Entidad Curso con atributos validados y mapeados con JPA.
* Script SQL incluido para carga inicial de datos.
* Configuración basada en `application.yml`.

---

## Responsables

| Rol                     | Nombre          | Usuario GitHub   | Observaciones |
|-------------------------|------------------|------------------|---------------|
| Autor del microservicio | Santiago García | @Santi202305 | Desarrollo de CRUD y clientes REST |
| Integración externa     | Santiago García | @Santi202305 | Conexión a Semestre y Docente |
| DevOps                  | —               | —                | Pendiente de Dockerfile |

---

Fecha: 2025-11-11

### Cambios relevantes

* Implementación completa del CRUD de Curso.
* Manejo de excepciones centralizado.
* Integración con los microservicios de Semestre y Docente.
* Organización del proyecto en capas (delivery, domain, infraestructura HTTP).

---

