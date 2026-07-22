# Organización y Roles - Plataforma de Gestión de Laboratorios

## Objetivo

Definir una estructura organizacional ágil (Modelo Spotify) que permita administrar eficientemente los laboratorios, cubriendo recursos físicos, imágenes de software y horarios de uso, combinando autonomía técnica con alineación metodológica (Wilber Guerra).

## Estructura ágil (Modelo Spotify)

### Tribe Platform Lab
Responsable de coordinar el proyecto completo. Podría dividirse en dos tribes en una fase 2, cuando las necesidades del "cliente" difieran claramente (estudiante vs. empresa) (Fernando Luque).

### Squads

- **Squad Core Platform**: arquitectura principal, integración de componentes, APIs.
- **Squad Image & Container Management**: Harbor, Docker, versionado de imágenes.
- **Squad Hardware & Lab Operations**: inventario, reservas, hardware.
- **Squad Frontend**: portal web, dashboards, experiencia del usuario.

### Chapters
Backend, DevOps, Frontend, Seguridad, Organización y Procesos. Cada Chapter define estándares técnicos y brinda mentoría.

### Guilds (a activar formalmente)
Actualmente mencionados solo a nivel teórico, sin activación formal. Se propone iniciar con (Wilber Guerra):
- **Guild de Seguridad**: escaneo de vulnerabilidades, gestión de identidad.
- **Guild de Automatización**: transversal a los equipos de desarrollo.

### Process Owner
Cada Squad debe contar con un responsable encargado de documentar procesos, mantener actualizada la matriz RACI y coordinar con el Chapter de Organización.
- Riesgo identificado: con una dedicación semanal de 15-25 horas, las urgencias técnicas pueden absorber a este rol y dejar de lado la documentación.
- Mitigación propuesta: bloquear explícitamente un 20% de su capacidad semanal (3-5 horas) exclusivamente para labores de Organización y Métodos (Wilber Guerra).

## Roles operativos (vista de procesos)

| Rol | Responsabilidad principal |
|---|---|
| **Director de Laboratorio** | Aprueba políticas generales, presupuesto y estándares de imágenes/licencias. |
| **Encargado / Administrador de Laboratorio** | Gestiona recursos, aprueba solicitudes, supervisa infraestructura, administra catálogo de imágenes, horarios y mantenimiento de equipos. |
| **Profesor / Docente** | Solicita imágenes y horarios para sus cursos, define requerimientos académicos, valida entornos y contenido técnico requerido. |
| **Alumno / Estudiante** | Usa los recursos e imágenes oficiales asignados, reporta incidencias, cumple políticas de uso. |
| **Administrador de Sistemas / DevOps** | Gestiona la infraestructura (Harbor, Kubernetes, GitLab), administra imágenes Docker, automatiza despliegues, supervisa seguridad. |
| **Equipo de Soporte** | Resuelve incidentes, actualiza infraestructura, mantiene la disponibilidad del servicio. |

(Síntesis a partir de Jaime Igreda y Jhon Cuyo; ambos coinciden en la necesidad de roles y responsabilidades explícitas para cada actor.)

## Flujo general de procesos

Solicitud → Validación → Creación de Imagen → Escaneo → Publicación → Uso → Retroalimentación (Jaime Igreda).

Procesos clave detallados por Jhon Cuyo:
1. **Pedido de imágenes para cursos**: el docente solicita indicando curso, software y versión → el encargado revisa si la imagen existe en Harbor → si no existe, se crea/importa y se escanea (Trivy) → el director o encargado aprueba la publicación → la imagen queda disponible para el curso.
2. **Separación de horarios de laboratorio por curso/proyecto**: el docente solicita bloques horarios según el sílabo → el encargado valida disponibilidad de equipos/salas → se asigna el horario en el calendario compartido.

## Matriz RACI

La matriz RACI cubre actualmente 6 actividades (Fernando Luque):
- Solicitud de Hardware
- Solicitud/Aprobación de Imágenes
- Creación de Imagen
- Reserva de Equipos
- Actualización de Imágenes
- Definición de Procesos

**Propuesta de nueva actividad — Monitoreo de Infraestructura / Gestión de Incidentes** (Fernando Luque):

| Rol | Responsabilidad |
|---|---|
| R (Responsable) | Squad Core Platform / Chapter DevOps |
| A (Aprueba) | Administrador de Laboratorio |
| C (Consultado) | Responsable de Imágenes (cuando el incidente es sobre una imagen específica) |
| I (Informado) | Docente, Estudiante |

## Riesgos organizacionales a considerar

- Sobrecarga del Process Owner por urgencias técnicas del squad (Wilber Guerra).
- Falta de detalle en los procesos de aprobación de horarios e imágenes por parte de roles administrativos (director, encargado) (Jhon Cuyo).
- Tensión autonomía vs. alineación entre squads: más autonomía sin alineación genera duplicados; más alineación sin autonomía genera demoras (Fernando Luque).
