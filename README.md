# Sanos y Salvos / PetFind

## Descripción del Proyecto
Sanos y Salvos (PetFind) es una plataforma móvil diseñada para facilitar la búsqueda y recuperación de mascotas perdidas. El sistema centraliza y automatiza reportes de mascotas perdidas y encontradas, utiliza geolocalización, genera coincidencias automáticas y envía notificaciones en tiempo real.

## Objetivos
- Centralizar reportes de mascotas perdidas y encontradas.
- Mejorar la coordinación entre dueños, rescatistas, clínicas veterinarias y organizaciones.
- Usar geolocalización para visualizar reportes en mapas interactivos.
- Automáticamente comparar reportes según raza, color, tamaño, ubicación y fecha.
- Escalar con una arquitectura de microservicios y asegurar calidad con SonarQube.

## Arquitectura del Sistema
El sistema se basa en una arquitectura de microservicios para separar responsabilidades, mejorar la escalabilidad y aumentar la resiliencia.

### Componentes principales
- API Gateway / BFF: Punto central de entrada para la aplicación móvil.
- Microservicio de Usuarios: Autenticación y gestión de usuarios.
- Microservicio de Mascotas: Administración de reportes de mascotas perdidas y encontradas.
- Microservicio Geoservice: Gestión de datos geográficos, ubicación y puntos de interés.
- Motor de Coincidencias: Algoritmo que compara reportes y genera coincidencias potenciales.
- Message Broker: Canal asíncrono para eventos y procesamiento fuera de línea.

### Modelo de comunicación
- Comunicación síncrona: HTTPS/REST para acciones con respuesta inmediata.
- Comunicación asíncrona: eventos para procesos pesados de análisis y coincidencias.
- Flujo de notificaciones: coincidencias detectadas -> gateway -> notificación a la app.

## Tecnologías Implementadas
- Android Jetpack Compose para la interfaz móvil.
- Kotlin para el desarrollo de la aplicación.
- Retrofit para consumo de APIs REST.
- Spring Boot para el backend.
- Spring Data JPA para la persistencia.
- Docker para contenerización.
- SonarQube para análisis de calidad de código.
- Git Flow para el manejo de ramas y el flujo de trabajo.

## Estrategia de Testing
La estrategia de pruebas combina pruebas funcionales, unitarias y análisis estático de código.

### Objetivos de las pruebas
- Verificar que los requisitos funcionales cumplan los criterios de aceptación.
- Validar reglas de negocio como registro de usuarios, reportes completos y autorizaciones.
- Detectar errores temprano para reducir costos de corrección.
- Medir calidad técnica con SonarQube.

### Alcance de las pruebas
- Gestión de usuarios.
- Administración de mascotas y reportes.
- Geolocalización y visualización en mapas.
- Motor de coincidencias inteligente.
- Notificaciones automáticas.
- Lógica en la capa Service de los microservicios.

### Pruebas unitarias en la capa Service
- Validación de registro e inicio de sesión de usuarios.
- Creación, modificación y cierre de reportes de mascotas.
- Gestión de coordenadas y reportes cercanos.
- Algoritmos de coincidencias de mascotas.

## Historias de Usuario
### Gestión de Usuarios
- Registro de usuario con nombre, correo y contraseña.
- Inicio de sesión con validación de credenciales.

### Gestión de Reportes de Mascotas
- Reportar mascota perdida con datos completos y fotografías.
- Reportar mascota encontrada y permitir comparaciones automáticas.
- Actualizar y cerrar reportes con historial almacenado.

### Geolocalización y Visualización
- Visualizar reportes en un mapa interactivo.
- Mostrar veterinarias y refugios cercanos.

### Motor de Coincidencias Inteligentes
- Comparar reportes según raza, color, tamaño, ubicación y fecha.
- Generar coincidencias potenciales y almacenarlas.

### Notificaciones
- Enviar alertas push cuando exista una posible coincidencia.
- Incluir información básica y acceso al detalle de la coincidencia.

### Validación de Coincidencias
- Permitir al dueño confirmar o rechazar coincidencias propuestas.
- Registrar la decisión y actualizar el estado del reporte.

## Fortalezas del Sistema
- Solución centrada en la problemática social de mascotas perdidas.
- Arquitectura basada en microservicios para escalabilidad.
- Uso de geolocalización y coincidencias automáticas.
- Enfoque en calidad de software con SonarQube.

## Debilidades y Riesgos
- Requiere disponibilidad de servicios distribuidos y mensajería.
- Dependencia de la adopción de la app por parte de usuarios.
- Necesidad de mantener la calidad de datos de reportes y ubicaciones.

## Generales
- Proyecto académico avalado por la asignatura DSY1106-002D.
- Docente: Viviana Poblete.
- Integrantes: Daniel Onetto y Constanza Orellana.

## Archivos relevantes
- `Desarrollo de sistema software PetFind.docx`: documento principal del proyecto.
- `Links xano.pdf`: enlaces y recursos relacionados.
- `Comunicación entre microservicios.png`: diagrama de comunicación.
- `Diagrama Arquitectura.png`: diagrama de arquitectura.
- `Patrón de Microservicios.png`: descripción del patrón de microservicios.

## Notas
El README se basa en el documento de análisis y diseño, por lo que puede complementarse con detalles de implementación específicos según avance el desarrollo del proyecto.
