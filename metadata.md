# Información de Datos

## Datos Estructurados

### Tabla de Vueltas

- **Fuente de los Datos**: [Ergast](https://ergast.com/mrd/)
- **Fecha de Recogida**: 20 octubre 2024
- **Formato de los Datos**: CSV
- **Licencia de Uso**: Apache License Version 2.0
- **Descripción de las Variables**:

| Variable      | Tipo       | Descripción                                                                                                      |
|---------------|------------|------------------------------------------------------------------------------------------------------------------|
| `raceId`      | INTEGER    | Identificador único para cada carrera, usado para asociar vueltas y pilotos con su carrera correspondiente.     |
| `driverId`    | INTEGER    | Identificador único para cada piloto, utilizado para vincular vueltas y posiciones a un piloto específico.      |
| `lap`         | INTEGER    | Número de la vuelta, comenzando desde `1` y aumentando hasta el total de vueltas de la carrera.                |
| `position`    | INTEGER    | Posición del piloto al final de la vuelta, donde `1` representa el primer lugar.                               |
| `time`        | TEXT       | Tiempo que le tomó al piloto completar la vuelta.                                                               |
| `milliseconds`| INTEGER    | Tiempo de la vuelta en milisegundos.                                                                            |

### Tabla de Conductores

- **Fuente de los Datos**: [Ergast](https://ergast.com/mrd/)
- **Fecha de Recogida**: 26 octubre 2024
- **Formato de los Datos**: CSV
- **Licencia de Uso**: Apache License Version 2.0
- **Descripción de las Variables**:

| Variable     | Tipo       | Descripción                                                                                     |
|--------------|------------|-------------------------------------------------------------------------------------------------|
| `driverId`   | INTEGER    | Identificador único del conductor.                                                              |
| `driverRef`  | TEXT       | Referencia al nombre del piloto, generalmente es su apellido.                                   |
| `number`     | INTEGER    | Número del piloto.                                                                              |
| `code`       | TEXT       | Código específico relacionado con el conductor.                                                 |
| `forename`   | TEXT       | Nombre del conductor.                                                                           |
| `surname`    | TEXT       | Apellido del conductor.                                                                         |
| `dob`        | DATE       | Fecha de nacimiento del conductor en formato `AAAA-MM-DD`.                                      |
| `nationality`| TEXT       | Nacionalidad del conductor.                                                                     |
| `url`        | TEXT       | Enlace a la página de Wikipedia del conductor.                                                  |

### Tabla de Carreras

- **Fuente de los Datos**: [Ergast](https://ergast.com/mrd/)
- **Fecha de Recogida**: 20 octubre 2024
- **Formato de los Datos**: CSV
- **Licencia de Uso**: Apache License Version 2.0
- **Descripción de las Variables**:

| Variable       | Tipo       | Descripción                                                                                                          |
|----------------|------------|----------------------------------------------------------------------------------------------------------------------|
| `raceId`       | INTEGER    | Identificador único de cada carrera, usado para asociar vueltas y pilotos con su carrera correspondiente.           |
| `year`         | INTEGER    | Año en que se lleva a cabo la carrera.                                                                               |
| `round`        | INTEGER    | Orden de la carrera dentro de la temporada.                                                                          |
| `circuitId`    | INTEGER    | Identificador del circuito donde se celebra la carrera.                                                              |
| `name`         | TEXT       | Nombre de la carrera.                                                                                                |
| `date`         | DATE       | Fecha de la carrera.                                                                                                 |
| `time`         | TIME       | Hora de inicio de la carrera.                                                                                        |
| `url`          | TEXT       | Enlace a la página de Wikipedia de la carrera.                                                                       |
| `fp1_date`     | DATE       | Fecha de la primera sesión de práctica (FP1), puede ser nula (`\N`).                                                 |
| `fp1_time`     | TIME       | Hora de la primera sesión de práctica (FP1), puede ser nula (`\N`).                                                  |
| `fp2_date`     | DATE       | Fecha de la segunda sesión de práctica (FP2), puede ser nula (`\N`).                                                 |
| `fp2_time`     | TIME       | Hora de la segunda sesión de práctica (FP2), puede ser nula (`\N`).                                                  |
| `fp3_date`     | DATE       | Fecha de la tercera sesión de práctica (FP3), puede ser nula (`\N`).                                                 |
| `fp3_time`     | TIME       | Hora de la tercera sesión de práctica (FP3), puede ser nula (`\N`).                                                  |
| `quali_date`   | DATE       | Fecha de la sesión de clasificación, puede ser nula (`\N`).                                                          |
| `quali_time`   | TIME       | Hora de la sesión de clasificación, puede ser nula (`\N`).                                                           |
| `sprint_date`  | DATE       | Fecha de la sesión de sprint, puede ser nula (`\N`).                                                                 |
| `sprint_time`  | TIME       | Hora de la sesión de sprint, puede ser nula (`\N`).                                                                  |





## Datos No Estructurados

- **Fuente de los datos**: Wikipedia de cada uno de los pilotos.
- **Fecha de Recogida**: 26 de octubre 2024 a las 17:37
- **Formato de los Datos**: JSONL
- **Licencia de Uso**: Licencia Creative Commons Atribución-CompartirIgual 4.0
- **Descripción de los Datos**: JSON por piloto que contiene `driverID` y el contenido de la primera sección de la entrada de Wikipedia del piloto. Permite realizar consultas sobre la descripción de cada piloto.




## Datos Enlazados

### Ontología de Carreras

Los datos estructurados y no estructurados están enlazados mediante una ontología RDF, diseñada para representar relaciones clave entre carreras, vueltas, y conductores, proporcionando una estructura formal para su uso en consultas y análisis semánticos.

#### Clases y Propiedades

- **Clases Principales**:
  - `ont:Driver`: Representa un dataset de pilotos.
  - `ont:Race`: Representa un dataset de carreras.
  - `ont:Lap`: Representa un dataset de vueltas.
  - `ont:Dataset`: Representa un conjunto de datos dentro del catálogo de datos.
  - `ont:DataCatalog`: Representa un catálogo que agrupa varios conjuntos de datos.

- **Propiedades de los Datos**:
  - Se ha descrito una data property para cada uno de los datos de los diferentes datasets.

- **Propiedades de los Objetos**:
  - `ont:hasDriver`: Relaciona una vuelta con el piloto correspondiente.
  - `ont:hasRace`: Asocia una vuelta con una carrera.
  - `ont:isPartOf`: Relaciona un conjunto de datos con su catálogo de datos correspondiente.

#### Catálogo de Datos y Conjuntos de Datos

- **ont:RacingDataCatalog**: Catálogo principal que agrupa conjuntos de datos sobre carreras, pilotos, y vueltas.
- **Conjuntos de datos individuales**:
  - `ont:LapData`: Contiene tiempos de vuelta y posiciones de pilotos.
  - `ont:RaceData`: Información de eventos de carrera.
  - `ont:DriverData`: Información sobre los pilotos, incluyendo datos personales y de carrera.
  - `ont:DriversDescriptions`: Descripciones textuales de los pilotos.

