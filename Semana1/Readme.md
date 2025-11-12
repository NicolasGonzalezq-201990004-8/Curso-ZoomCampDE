# Apuntes Docker + Postgres
Docker: Entrega software en paquetes (contenedores) aislados. Permite ejecutar Pipelines de manera aislada.

Data Pipelines: Proceso o servicio que recibe como input data, la transforma y la entrega como output. Ejemplo: Script de python recibe un csv, transforma dicha data y la entrega tablas en Postgres. 
Varios proceso ocurriendo de manera simultánea o en cadena también corresponden a un Data Pipeline.

Consideremos que tenemos un host en windows. En esta máquina pueden estár corriendo varios contenedores de la siguiente manera:

Contenedor 1: 
* Data Pipeline en Ubuntu 20.04 con las siguientes dependencias:
  *   Python 3.9.
  *   Pandas.
  *   Postgres connection library (El data Pipeline se debe comunicar con Postgres).

Contenedor 2: 
* Postgres BD.

Contenedor 3:
* Postgres BD.

### Nota: Las bases de datos de contendores 2 y 3 no harán conflicto entre sí, tampoco lo harán con alguna BD Postgres que pueda estár instalada en el equipo host. Recordar propiedad de aislamiento que poseen los contendores.

Contenedor 3: 
* PgAdmin: Es posible tener pgAdmin instalado en un contenedor y que este se comunique con el contenedor que posee las bases de datos Postgres, sin necesidad de tenerlo en el equipo Host.

La utilización de contenedores nos entrega:
* Reproducibilidad.
* Experimentos locales.
* Test de integración: Útil para Entrega/Integración continua.
* Ejecución en la nube.
* Spark.
