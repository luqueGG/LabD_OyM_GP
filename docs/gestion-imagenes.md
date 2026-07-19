# Gestión de Imágenes y Trazabilidad

## Flujo Principal

1. Solicitud de imagen (Proyecto o Curso)
2. Búsqueda automática en Harbor
3. Si no existe → Responsable revisa y aprueba creación
<span style="color:red;">**[COMENTARIO EN CONTRA]:** El KPI de "≤ 48 horas" para aprobación manual es un cuello de botella inaceptable en un entorno ágil y bloquea el avance del estudiante. Se debe implementar un "Fast-Track": si la imagen solicitada se basa en una plantilla oficial de la cátedra, el escaneo (Trivy) y la publicación deben ser automáticos en minutos, saltando la revisión manual.</span>
4. Escaneo de vulnerabilidades (Trivy)
5. Firma de imagen
6. Publicación con metadatos de trazabilidad
7. Estudiantes pueden descargar la imagen oficial

**Beneficio clave:** Los alumnos trabajan con el **mismo entorno** dentro y fuera del laboratorio.