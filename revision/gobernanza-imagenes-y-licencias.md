# 2.2 Gobernanza de Imágenes Docker, Software y Licencias

## 1. Necesidad de Gobernanza
Sin un proceso formal de gobernanza, los laboratorios acumulan imágenes duplicadas, software sin licencia válida y versiones inconsistentes entre cursos, lo que genera riesgos de seguridad, incumplimiento legal y pérdida de trazabilidad.

## 2. Puntos Clave a Gestionar

### 2.1 Gobernanza de Imágenes Docker
- Catálogo único y versionado en un registry central (Harbor).
- Escaneo obligatorio de vulnerabilidades antes de publicar (ej. Trivy).
- Firma digital de imágenes aprobadas para garantizar integridad.
- Ciclo de vida definido: creación, aprobación, publicación, deprecación.

### 2.2 Gestión de Licencias de Software
- Registro centralizado de licencias (tipo, vigencia, cantidad de usuarios permitidos).
- Validación de que el software incluido en las imágenes cumpla con los términos de licencia (especialmente en el contexto empresarial).
- Alertas automáticas antes del vencimiento de licencias.

### 2.3 Trazabilidad
- Cada imagen debe registrar: autor, fecha, curso/proyecto asociado, software y licencias incluidas.
- Los logs de descarga y uso permiten auditar qué se usó, cuándo y por quién.
- La trazabilidad es crítica para pasar de un entorno académico a uno empresarial, donde el cumplimiento normativo (compliance) es obligatorio.

## 3. Beneficios
- Reduce riesgos legales por uso de software sin licencia.
- Facilita auditorías internas y externas.
- Da confianza para escalar la plataforma del proyecto universitario al proyecto empresarial.
