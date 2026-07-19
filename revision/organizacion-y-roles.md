# 2.1 Definición de Organización y Roles

## 1. Actores Involucrados

| Rol | Responsabilidad principal |
|---|---|
| **Director de Laboratorio** | Aprueba políticas generales, presupuesto y estándares de imágenes/licencias. |
| **Encargado de Laboratorio** | Administra el catálogo de imágenes, horarios y mantenimiento de equipos. |
| **Profesor / Docente** | Solicita imágenes y horarios para sus cursos, valida el contenido técnico requerido. |
| **Alumno** | Usa los recursos asignados, reporta incidencias, descarga imágenes oficiales para uso personal. |
| **Administrador de Sistemas / DevOps** | Gestiona la infraestructura (Harbor, Kubernetes, GitLab) y ejecuta los procesos técnicos de publicación de imágenes. |

## 2. Procesos Clave

### 2.1.1 Pedido de Imágenes para Cursos
1. El profesor completa una solicitud indicando curso, software requerido y versión.
2. El encargado de laboratorio revisa si la imagen ya existe en el catálogo (Harbor).
3. Si no existe, se crea/importa la imagen y pasa por escaneo de seguridad (Trivy).
4. El director o encargado aprueba la publicación.
5. La imagen queda disponible para el curso y descargable por los alumnos.

### 2.1.2 Separación de Horarios de Laboratorio por Curso/Proyecto
1. El profesor solicita bloques horarios según el sílabo del curso.
2. El encargado de laboratorio valida disponibilidad de equipos/salas.
3. Se asigna el horario en el calendario compartido, con prioridad definida por reglas institucionales (evaluaciones, proyectos con fecha límite, etc.).
4. Los conflictos de horario se resuelven entre encargado y profesores involucrados, con el director como última instancia.

## 3. Flujo de Escalamiento
Alumno → Profesor → Encargado de Laboratorio → Director (solo para decisiones de presupuesto o políticas generales).


