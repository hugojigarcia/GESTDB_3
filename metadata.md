Tabla de vueltas:

• Fuente de los Datos: [Ergast](https://ergast.com/mrd/).

• Fecha de Recogida: 20 octubre 2024.

• Formato de los Datos: CSV.

• Licencia de Uso:    Apache License Version 2.0.

• Descripción de las Variables o Atributos: 

- **raceId**: Identificador único de tipo `INTEGER` para cada carrera, utilizado para relacionar las vueltas y los pilotos con la carrera correspondiente.
- **driverId**: Identificador único de tipo `INTEGER`, que representa de manera única a cada piloto y se usa para asociar las vueltas y posiciones a un piloto específico.
- **lap**: Número entero que indica el número de la vuelta que se está registrando, comenzando desde `1` y aumentando hasta el total de vueltas de la carrera.
- **position**: Número entero que indica la posición del piloto al final de la vuelta, donde `1` representa el primer lugar.
- **time**: Campo de tipo `TEXT` que registra el tiempo que le tomó al piloto completar la vuelta.
- **milliseconds**: Número entero que representa el tiempo de la vuelta en milisegundos.

Tabla de conductores:

• Fuente de los Datos: API de https://github.com/jolpica/jolpica-f1/tree/main.

• Fecha de Recogida: 20 octubre 2024.• Formato de los Datos:  JSON.

• Licencia de Uso:    Apache License Version 2.0.

• Descripción de las Variables o Atributos: 

- **driverId**: Es una clave única que identifica a cada conductor. Cada valor en esta columna representa un identificador corto y exclusivo.
- **url**: Proporciona un enlace a la página de Wikipedia del conductor. Este enlace contiene más información sobre el historial y carrera del conductor.
- **familyName**: Es el apellido o el nombre de familia del conductor.
- **dateOfBirth**: Indica la fecha de nacimiento de cada conductor en el formato "AAAA-MM-DD"
- **nationality**: Contiene la nacionalidad del conductor. 
- **permanentNumber**: Este campo parece estar relacionado con un número de identificación permanente para los conductores.
- **code**: Es un código específico relacionado con los conductores,

Tabla de carreras:

• Fuente de los Datos: [Ergast](https://ergast.com/mrd/).

• Fecha de Recogida: 20 octubre 2024.

• Formato de los Datos:CSV.

• Licencia de Uso:    Apache License Version 2.0.

• Descripción de las Variables o Atributos: 

- **raceId**: Identificador único de tipo `INTEGER` para cada carrera, utilizado para relacionar las vueltas y los pilotos con la carrera correspondiente.
- **year**: Año en que se lleva a cabo la carrera, representado como un número entero.
- **round**: Número entero que indica el orden de la carrera dentro de la temporada.
- **circuitId**: Identificador del circuito donde se celebra la carrera, generalmente representado como un número entero.
- **name**: Nombre de la carrera, presentado como un texto.
- **date**: Fecha en que se celebra la carrera, en formato `DATE`.
- **time**: Hora de inicio de la carrera, en formato `TIME`.
- **url**: Enlace a la página de Wikipedia de la carrera, presentado como un texto.
- **fp1_date, fp1_time, fp2_date, fp2_time, fp3_date, fp3_time**: Fechas y horas de las sesiones de práctica (FP1, FP2, FP3) que pueden ser nulas (representadas como `\N`).
- **quali_date, quali_time**: Fecha y hora de la sesión de clasificación que pueden ser nulas (representadas como `\N`).
- **sprint_date, sprint_time**: Fecha y hora de la sesión de sprint que pueden ser nulas (representadas como `\N`).
