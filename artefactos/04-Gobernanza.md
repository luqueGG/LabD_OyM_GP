# Gobernanza de Imágenes Docker y Licencias - Plataforma de Gestión de Laboratorios

## 1. Justificación

La gobernanza de imágenes Docker garantiza que todos los usuarios trabajen sobre entornos controlados, seguros y reproducibles. Sin ella pueden presentarse (Jaime Igreda, Fernando Luque):

- Diferencias entre entornos ("funciona en mi máquina") (también señalado por Jhon Cuyo).
- Vulnerabilidades de seguridad.
- Uso de software sin licencia.
- Pérdida de trazabilidad.
- Dificultad para reproducir prácticas.
- Imágenes duplicadas y versiones inconsistentes entre cursos, con riesgos legales y de seguridad (Jhon Cuyo).

## 2. Gobernanza de imágenes Docker

Toda imagen que forme parte de la plataforma debe mantenerse bajo un proceso de control que permita identificar responsable, versión y cambios a lo largo del tiempo. Antes de publicarse en el repositorio central, cada imagen debe pasar por un proceso de validación que verifique su correcto funcionamiento y descarte vulnerabilidades (Diego Santa Cruz, Fernando Luque).

**Ciclo de vida y buenas prácticas identificadas por el equipo:**
- Catálogo único y versionado en un registry central (Harbor) (Jhon Cuyo, Diego Santa Cruz).
- Escaneo obligatorio de vulnerabilidades antes de publicar (ej. Trivy) (Jhon Cuyo, Jaime Igreda).
- Firma digital de imágenes aprobadas para garantizar integridad (Jhon Cuyo, Jaime Igreda).
- Ciclo de vida definido: creación, aprobación, publicación, deprecación (Jhon Cuyo).
- Eliminar imágenes obsoletas (Jaime Igreda).
- Registrar responsable, fecha y cambios de cada imagen (Jaime Igreda).
- Mantener historial de versiones para poder recuperar imágenes anteriores (Diego Santa Cruz, Jaime Igreda).
- Automatizar el escaneo de vulnerabilidades mediante integración continua (Jaime Igreda).

**Cuello de botella detectado**: el flujo actual exige revisión manual cuando la imagen no existe en Harbor, con un KPI de "≤48 horas". Se propone un fast-track: si la imagen se basa en plantillas oficiales preaprobadas, se omite la revisión manual y se realiza solo el escaneo automático de seguridad antes de publicar (Wilber Guerra).

## 3. Uso de Harbor

Harbor se plantea como repositorio central de imágenes y debe convertirse en el punto único de almacenamiento y distribución. Esto permite controlar qué imágenes puede usar cada equipo, gestionar permisos de acceso y mantener un registro de actualizaciones. Harbor facilita la trazabilidad y contribuye a un entorno estandarizado tanto para la versión académica como para la empresarial (Diego Santa Cruz).

## 4. Gestión de licencias

Es necesario llevar un registro de las licencias de todas las tecnologías y dependencias empleadas por el proyecto. Para cada herramienta se recomienda documentar nombre, versión y tipo de licencia, verificando compatibilidad con los objetivos del proyecto y evitando inconvenientes legales por uso de software de terceros (Diego Santa Cruz).

**Puntos clave a gestionar (Jhon Cuyo):**
- Registro centralizado de licencias: tipo, vigencia y cantidad de usuarios permitidos.
- Validación de que el software incluido en las imágenes cumpla los términos de licencia, especialmente en el contexto empresarial.
- Alertas automáticas antes del vencimiento de licencias.
- Control de licencias del sistema operativo, software comercial, dependencias e imágenes base Docker (Jaime Igreda).

Se señala como un vacío importante que el proyecto aún **no especifica cómo se gestionarán las licencias de software en el catálogo de imágenes**, lo cual es crítico para la versión empresarial; se recomienda incluir un documento específico de gobernanza de imágenes y licencias (Jhon Cuyo).

## 5. Trazabilidad

La trazabilidad permite conocer (Jaime Igreda, Jhon Cuyo):
- Quién creó/solicitó una imagen y cuándo fue publicada.
- Qué versión se encuentra en producción y qué cambios contiene.
- Qué software y licencias incorpora.
- Para qué curso/proyecto fue solicitada.
- Los logs de descarga y uso, con fines de auditoría.

Esta trazabilidad es considerada crítica para escalar de un entorno académico a uno empresarial, donde el cumplimiento normativo (compliance) es obligatorio (Jhon Cuyo).

## 6. Beneficios esperados

- Reducción de riesgos legales por uso de software sin licencia.
- Facilita auditorías internas y externas.
- Da confianza para escalar la plataforma del proyecto universitario al proyecto empresarial (Jhon Cuyo).
- Entornos controlados, seguros y reproducibles para todos los usuarios (Jaime Igreda).
