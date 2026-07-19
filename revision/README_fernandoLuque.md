# Propuesta - Gestion de Laboratorios

Autor: Fernando Gerson Luque Guevara


## COMENTARIO
Acerca de los procesos de laboratorio entre *complejo* y *complicado*; segun Cynefin
la **reservacion y uso de laboratorios** es complicado en el sentido de que existen
reglas fijas.

En cambio la decision respecto a "una imagen Oficial" y "crear una", va a depender
del responsable o si es que hay dos, muy probable que haya puntos de postura diferentes
lo que es complejo.

### Leyendo la documentacion
Se menciona una pregunta acerca de como dividir "Platform Lab" en dos tribes?

Bueno yo pienso que cuando las necesidades son distintas para la vision del producto.
Es cuando entramos en la fase 2, porque ya no es el mismo cliente; sino estudiante y empresa.

### Acerca de indicadores
Tenemos KPIs como el tiempo de aprobacion y automatizado, pero si lo pensamos,
sabremos que miden el producto.

Y que hay de la organizacion?

Se menciona una interrogante entre autonomia vs alineacion

#### Autonomia
- Decisiones tecnicas dentro de un squad
- Tambien el tiempo promedio entre:
    - Squad identifica un problema
    - Piensa
    - Encuentra una solucion

#### Alineacion
- Los procesos documentados por el Process Owner que fueron revisados y validados por el Chapter de Organización dentro del plazo.
- Consistencia entre squads
- Saber cuantas actividades tienen responsables compartidos en los squads

Si identificamos
```
Si la autonomia sube pero la alineacion baja -> habrá mas duplicados
en cambio
Si la alineacion sube pero la autonomia baja -> Habrá mas demoras
```

## PROPUESTA DE PROCESO
- Una computadora en un laboratorio al encencerse aparece una interfaz pidiendo credenciales (lo que la universidad provee a su alumnado)
- Con ello podremos mapear y registrar los movimientos que hacen los alumnos por una de sus "bromitas".
- Trazabilidad operativa no para el usuario, sino para los programas, esto con el objetivo de telemetria, logs para saber que estan en orden o si hay algun error o inconveniente, saber que esta pasando
- Cada usuario tendra accesos a las herramientas necesarias para la carrera, todas las maquinas por igual

### Como se relaciona con la documentacion?
- El login con credenciales institucionales al encender la máquina es exactamente lo que ya cubre Keycloak en **aarquitecutra.md**. Esto no es una feature adicional, es la materialización de la Épica 2.
- "Todas las maquinas por igual", significa que los alumnos trabajan con el mismo entorno. Esto sin romper la diferenciacion de roles que ya existe.
- Épica 4 ya pide "Monitoreo del estado de los laboratorios" — telemetría de programas/servicios es literalmente eso.
- En procesos-laboratorio.md tiene KPIs que hoy no tienen mecanismo claro de medición automática (ej. "tiempo promedio de configuración de entorno ≤15 min", "tasa de utilización de imágenes oficiales ≥75%"). Sin logs/telemetría, esos KPIs se medirían manualmente o con encuestas, lo cual es poco confiable. Con telemetría de programas, esos KPIs se vuelven medibles automáticamente.

## Para ello
tendriamos que agregar stack tecnologico en arquitectura.md como
Prometheus + Grafana para métricas, Loki o ELK para logs. Lo que es el stack estándar que ya usa el ecosistema Kubernetes. Esto para la salud de la infraestructura.