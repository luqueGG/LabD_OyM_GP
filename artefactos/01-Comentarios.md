# Comentarios del Equipo - Plataforma de Gestión de Laboratorios

## Visión general

El equipo coincide en que la propuesta —basada en el Modelo Spotify y el marco Cynefin para justificar un enfoque de agilidad organizacional— constituye una base sólida y bien estructurada para resolver un problema real: la falta de estandarización y trazabilidad en la gestión de laboratorios universitarios (y, a futuro, empresariales).

## Aspectos positivos destacados

- **Claridad del problema y objetivos**: la documentación explica bien el problema que busca resolver la plataforma (Diego Santa Cruz).
- **Modelo Spotify adecuado**: Squads, Chapters y Guilds permiten organizar equipos con múltiples áreas de especialización y escalar de un proyecto académico a uno empresarial de forma ordenada (Diego Santa Cruz, Jhon Cuyo).
- **Uso de Cynefin**: catalogar la situación como un "problema complejo" justifica adecuadamente adoptar un modelo ágil que combine autonomía técnica (Squads) con alineación metodológica (Chapters) (Wilber Guerra).
- **Backlog con priorización MoSCoW** correctamente aplicado (Diego Santa Cruz).
- **Separación clara de responsabilidades** entre procesos, arquitectura y gestión de imágenes (Jaime Igreda).
- **Harbor como catálogo centralizado** de imágenes, evitando instalaciones manuales repetidas (Jhon Cuyo).
- **Flujo de gestión de imágenes trazable**: solicitud → escaneo (Trivy) → firma → publicación (Jhon Cuyo).

## Observaciones y vacíos identificados

### Documentación técnica y arquitectura
- Falta un **diagrama general de arquitectura técnica** que muestre la interacción entre Usuario, Plataforma, Harbor, Kubernetes, GitLab y Base de datos (Diego Santa Cruz).
- No existe una **guía de instalación** (INSTALL.md) que facilite la incorporación de nuevos colaboradores (Diego Santa Cruz).
- Falta describir en detalle el **flujo entre componentes tecnológicos** (Harbor, Kubernetes, GitLab, Keycloak, etc.) (Diego Santa Cruz).
- Sería útil un **glosario de términos técnicos** (Diego Santa Cruz).
- Hay **información repetida** entre la presentación y el documento principal que podría centralizarse (Diego Santa Cruz, Jaime Igreda).

### Procesos y eficiencia operativa
- **Duplicidad de flujos**: el Proceso 3.1 (Solicitud/Asignación de Hardware) y el Proceso 3.4 (Reserva y Uso de Laboratorio) representan, desde la perspectiva del estudiante, un mismo evento operativo, y mantenerlos separados genera fricción administrativa (Wilber Guerra).
- **Cuello de botella en aprobación de imágenes**: el KPI de "≤48 horas" para revisión manual es un bloqueo crítico en un entorno ágil; se propone un fast-track para imágenes basadas en plantillas oficiales preaprobadas (Wilber Guerra).
- **Ausencia de procesos de cierre de ciclo y contingencias**: no hay gestión de incidentes (fallas de hardware/servidor) ni procesos de limpieza/cierre de semestre para liberar almacenamiento en Proxmox y Harbor (Wilber Guerra, Fernando Luque).
- Los **KPIs actuales no tienen mecanismo automático de medición** (ej. tiempo de configuración de entorno, tasa de uso de imágenes oficiales); sin telemetría se medirían manualmente o por encuestas, lo cual es poco confiable (Fernando Luque).

### Organización y roles
- Riesgo de que el rol de **Process Owner** (estudiante, con 15-25 h/semana de dedicación) sea absorbido por urgencias técnicas, dejando de lado la documentación de procesos (Wilber Guerra).
- Los **Guilds** están mencionados en la fundamentación teórica pero no han sido activados formalmente en la estructura organizacional (Wilber Guerra).
- Falta definir con más detalle **roles administrativos** (director, encargado de laboratorio) y sus procesos de aprobación de horarios e imágenes (Jhon Cuyo).
- No hay **responsables explícitos** para todas las actividades críticas (Jaime Igreda).

### Indicadores, riesgos y licencias
- Falta definir **KPIs** para medir el desempeño de cada proceso (Jaime Igreda, Fernando Luque) y añadir indicadores de organización (no solo de producto), como tiempo de resolución de problemas a nivel de squad y consistencia entre squads (Fernando Luque).
- No hay una **matriz de riesgos** técnicos y organizacionales (Diego Santa Cruz), ni políticas de gestión de riesgos (Jaime Igreda).
- No se especifica cómo se gestionarán las **licencias de software** en el catálogo de imágenes, algo crítico para la versión empresarial (Jhon Cuyo, Diego Santa Cruz).
- Falta un **procedimiento formal de auditoría y control de cambios** (Jaime Igreda).

## Discusión conceptual (Fernando Luque)

- Bajo el marco Cynefin, la reservación y uso de laboratorios es más bien **complicado** (reglas fijas conocidas), mientras que la decisión entre usar una "imagen oficial" o crear una nueva es **compleja** (depende del responsable y puede haber posturas distintas).
- Sobre la división de "Platform Lab" en dos tribes: tendría sentido cuando las necesidades del cliente difieren (estudiante vs. empresa), es decir, en la fase 2 del proyecto.
- Existe una tensión entre **autonomía** (decisiones técnicas dentro del squad, tiempo de resolución de problemas) y **alineación** (procesos documentados y validados, consistencia entre squads): si sube la autonomía y baja la alineación, habrá más duplicados; si sube la alineación y baja la autonomía, habrá más demoras.

## Síntesis del equipo

- Estandarizar todos los procesos del laboratorio.
- Automatizar la gestión de imágenes Docker.
- Definir claramente los responsables de cada proceso.
- Implementar indicadores para evaluar el desempeño.
- Fortalecer la trazabilidad mediante control de versiones.
- Mejorar la documentación técnica y operativa.
