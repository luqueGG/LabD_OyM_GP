# Documento de revisión - Diego Sebastian Santa Cruz Villa

## Comentario

Después de analizar la documentación el presente repositorio, se observa que se presenta una propuesta bien estructurada para abordar la gestión de laboratorios mediante un enfoque organizacional basado en el Modelo Spotify y los principios de agilidad organizacional. La documentación permite comprender el contexto del problema, los objetivos del proyecto y la forma en que se pretende organizar el trabajo de los diferentes equipos involucrados.

Asimismo, el uso de documentos como el caso de estudio, la presentación del Modelo Spotify y el backlog inicial facilita entender la visión general del proyecto y la planificación de sus principales funcionalidades. La organización de la información mantiene una secuencia lógica que permite relacionar los conceptos teóricos con su aplicación en el caso propuesto.

No obstante, durante la revisión también se identificaron algunos aspectos que podrían mejorarse para fortalecer la documentación y facilitar tanto el desarrollo futuro del proyecto como la incorporación de nuevos colaboradores.

### Aspectos positivos 

- La documentación explica claramente el problema que busca resolver la plataforma.
- El uso del Modelo Spotify resulta adecuado para organizar equipos que trabajarán sobre un proyecto con múltiples áreas de especialización.
- El backlog utiliza correctamente la priorización MoSCoW.

### Aspectos por mejorar

1. El repositorio no incluye un diagrama general de arquitectura técnica de la plataforma.
2. No existe una guía de instalación facilitaría la participación de nuevos colaboradores y la validación del proyecto.
3. No existe una descripción detallada del flujo entre los distintos componentes tecnológicos (Harbor, Kubernetes, GitLab, Keycloak, etc.).
4. Sería conveniente incorporar un glosario de términos técnicos para facilitar la comprensión de nuevos integrantes.
5. Algunos documentos presentan información repetida entre la presentación y el documento principal, por lo que podría centralizarse parte del contenido.

---

## Propuestas de mejora

### Propuesta 1

Agregar un diagrama de arquitectura donde se muestre la interacción entre:

- Usuario
- Plataforma
- Harbor
- Kubernetes
- GitLab
- Base de datos

### Propuesta 2

Crear un documento INSTALL.md explicando cómo desplegar la plataforma paso a paso.

### Propuesta 3

Incorporar una matriz de riesgos técnicos y organizacionales.

### Propuesta 4

Agregar un cronograma tentativo para cada fase del proyecto.

### Propuesta 5

Definir indicadores (KPIs) para medir:

- Tiempo de despliegue
- Uso del laboratorio
- Disponibilidad
- Tiempo de recuperación

---

## Organización y Roles

### Tribe Platform Lab

Responsable de coordinar el proyecto completo.

### Squad Core Platform

Responsable de:

- Arquitectura principal
- Integración de componentes
- APIs

### Squad Image & Container Management

Responsable de:

- Harbor
- Docker
- Versionado de imágenes

### Squad Hardware & Lab Operations

Responsable de:

- Inventario
- Reservas
- Hardware

### Squad Frontend

Responsable de:

- Portal web
- Dashboards
- Experiencia del usuario

### Chapters

Backend
DevOps
Frontend
Seguridad
Organización y Procesos
Cada Chapter define estándares técnicos y brinda mentoría.

### Process Owner

Cada Squad debe contar con un responsable encargado de:
- Documentar procesos
- Mantener actualizada la matriz RACI
- Coordinar con el Chapter de Organización.

---

# Gobernanza de Imágenes Docker y Licencias

## Gobernanza de imágenes Docker

Toda imagen Docker que forme parte de la plataforma deberá mantenerse bajo un proceso de control que permita identificar su responsable, su versión y los cambios realizados a lo largo del tiempo. Antes de ser publicada en el repositorio central, cada imagen deberá pasar por un proceso de validación que verifique su correcto funcionamiento y descarte posibles vulnerabilidades de seguridad. Además, será importante mantener un historial de versiones para facilitar la recuperación de imágenes anteriores cuando sea necesario.

## Uso de Harbor

El proyecto plantea el uso de Harbor como repositorio central de imágenes, por lo que este deberá convertirse en el punto único de almacenamiento y distribución. Esto permitirá controlar qué imágenes pueden ser utilizadas por los diferentes equipos de trabajo, gestionar permisos de acceso y mantener un registro de las actualizaciones realizadas. Asimismo, Harbor facilitará la trazabilidad de las imágenes y contribuirá a mantener un entorno de trabajo estandarizado tanto para la versión académica como para la empresarial.

## Gobernanza de licencias

Además del control sobre las imágenes Docker, resulta necesario llevar un registro de las licencias correspondientes a todas las tecnologías y dependencias empleadas por el proyecto. Para cada herramienta utilizada se recomienda documentar su nombre, versión y tipo de licencia, verificando que su uso sea compatible con los objetivos del proyecto y evitando posibles inconvenientes legales derivados del uso de software de terceros.
