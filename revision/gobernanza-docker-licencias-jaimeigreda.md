# Gobernanza de Imágenes Docker y Gestión de Licencias

## Justificación

La gobernanza de imágenes Docker permite garantizar que todos los usuarios trabajen sobre entornos controlados, seguros y reproducibles.

Sin una adecuada gobernanza pueden presentarse problemas como:

- Diferencias entre entornos.
- Vulnerabilidades de seguridad.
- Uso de software sin licencia.
- Pérdida de trazabilidad.
- Dificultad para reproducir prácticas.

## Buenas prácticas

- Mantener un registro oficial de imágenes.
- Versionar todas las imágenes.
- Firmar imágenes oficiales.
- Escanear vulnerabilidades antes de publicar.
- Eliminar imágenes obsoletas.
- Registrar responsable, fecha y cambios.

## Gestión de Licencias

La empresa debe controlar:

- Licencias del sistema operativo.
- Licencias de software comercial.
- Dependencias utilizadas.
- Licencias de imágenes base Docker.

Esto evita incumplimientos legales y facilita auditorías.

## Importancia de la Trazabilidad

La trazabilidad permite conocer:

- quién creó una imagen;
- cuándo fue publicada;
- qué versión se encuentra en producción;
- qué cambios contiene;
- qué software incorpora;
- qué licencias posee.

De esta manera se garantiza la reproducibilidad, la seguridad y el cumplimiento normativo.
