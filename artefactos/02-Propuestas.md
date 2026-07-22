# Propuestas de Mejora - Plataforma de Gestión de Laboratorios

## 1. Documentación y arquitectura técnica

- **Diagrama de arquitectura general**, mostrando la interacción entre Usuario, Plataforma, Harbor, Kubernetes, GitLab y Base de datos (Diego Santa Cruz).
- **Documento INSTALL.md** con el paso a paso para desplegar la plataforma (Diego Santa Cruz).
- **Glosario de términos técnicos** para facilitar la incorporación de nuevos integrantes (Diego Santa Cruz).
- **Centralizar contenido duplicado** entre la presentación y el documento principal (Diego Santa Cruz).
- **Centralizar la documentación técnica** en general (Jaime Igreda).

## 2. Gestión de riesgos, KPIs y cronograma

- **Matriz de riesgos técnicos y organizacionales** (Diego Santa Cruz); políticas de gestión de riesgos (Jaime Igreda).
- **Cronograma tentativo** para cada fase del proyecto (Diego Santa Cruz).
- **Indicadores (KPIs)** para medir: tiempo de despliegue, uso del laboratorio, disponibilidad y tiempo de recuperación (Diego Santa Cruz); indicadores de desempeño para cada proceso (Jaime Igreda, Jhon Cuyo); métricas de utilización de laboratorios (Jaime Igreda).
- **Indicadores organizacionales**, no solo de producto: tiempo promedio entre que un squad identifica un problema y encuentra una solución; consistencia entre squads; cantidad de actividades con responsables compartidos (Fernando Luque).
- **Stack de observabilidad**: Prometheus + Grafana para métricas, Loki o ELK para logs, como estándar del ecosistema Kubernetes, para hacer medibles automáticamente KPIs como el tiempo de configuración de entorno o la tasa de uso de imágenes oficiales (Fernando Luque).

## 3. Simplificación y automatización de procesos operativos

- **Fusionar el Proceso 3.1 (Solicitud/Asignación de Hardware) y el 3.4 (Reserva y Uso de Laboratorio)** en un "Proceso Integrado de Reserva de Espacio de Trabajo": al validar horario y escanear el código QR, el sistema asignaría el hardware y prepararía automáticamente la imagen requerida en un solo paso (Wilber Guerra).
- **Fast-track para imágenes estándar**: si la solicitud se basa en plantillas oficiales preaprobadas, omitir la revisión manual, escanear automáticamente por seguridad y publicar, reduciendo el KPI de 48 horas a minutos (Wilber Guerra).
- **Login con credenciales institucionales al encender la máquina** (materialización de Keycloak/Épica 2), permitiendo mapear y registrar el uso de los equipos; mismo entorno para todos los estudiantes de una carrera, sin romper la diferenciación de roles (Fernando Luque).
- **Telemetría/logs de programas y servicios** (no solo del usuario) para monitoreo del estado de los laboratorios (Épica 4) y para medir KPIs automáticamente (Fernando Luque).
- **Automatizar el escaneo de vulnerabilidades** de imágenes Docker mediante integración continua (Jaime Igreda); escaneo obligatorio (ej. Trivy) antes de publicar (Jhon Cuyo).

## 4. Nuevos procesos críticos (ciclo de vida completo)

- **Gestión de Incidentes**: qué ocurre operativa y sistémicamente si falla un equipo físico o un servidor (Wilber Guerra, Fernando Luque).
- **Cierre/limpieza de semestre**: liberar almacenamiento en Proxmox y Harbor al finalizar el ciclo académico (Wilber Guerra).
- Reflejar estos procesos como nuevas Historias de Usuario en el backlog, bajo las Épicas 1 (Organización) y 4 (Hardware) (Wilber Guerra).
- **Políticas de respaldo y recuperación ante desastres** (Jaime Igreda).
- **Procedimiento formal de auditoría y control de cambios** (Jaime Igreda).

## 5. Ajustes al modelo ágil

- **Proteger las horas del Process Owner**: bloquear explícitamente un 20% de su capacidad semanal (3-5 horas) exclusivamente para labores de Organización y Métodos, para evitar que las urgencias técnicas absorban ese tiempo (Wilber Guerra).
- **Activar formalmente los Guilds**: iniciar con un Guild de Seguridad (escaneo de vulnerabilidades, gestión de identidad) y un Guild de Automatización transversal a los equipos de desarrollo (Wilber Guerra).

## 6. Procesos organizacionales (centralización, roles, calendario)

- **Centralización de solicitudes**: toda solicitud (imagen, horario, recurso físico) debe pasar por un único canal (plataforma/ticket), evitando acuerdos informales entre docente y encargado (Jhon Cuyo).
- **Catálogo estandarizado de imágenes** aprobadas por curso, evitando instalaciones manuales repetidas (Jhon Cuyo).
- **Calendario compartido de horarios** por curso/proyecto, con reglas de prioridad (ej. cursos con evaluación práctica tienen prioridad) (Jhon Cuyo).
- **Revisión periódica** (quincenal/mensual) del uso de laboratorios y del catálogo de imágenes, para retirar versiones obsoletas o inseguras (Jhon Cuyo).
- **Niveles de acceso por rol** para estudiantes, docentes y administradores (Jaime Igreda).
- **Procedimiento formal de aprobación** de nuevas imágenes (Jaime Igreda).
- **Historial de versiones** de imágenes Docker (Jaime Igreda).

## Impacto esperado

- Reducción del tiempo perdido en configuraciones manuales.
- Mayor transparencia en el uso de recursos.
- Mejor preparación de los alumnos para entornos profesionales.
- Menos duplicados y menos demoras, al equilibrar autonomía y alineación entre squads.
