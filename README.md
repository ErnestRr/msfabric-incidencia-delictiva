# Incidencia delictiva municipal en México
## # Arquitectura Medallion con datos abiertos al público

#### Este proyecto utiliza datos públicos de incidencia delictiva de México que abarca de 2019 a julio de 2025 a nivel mensual, la fuente de datos crudos son del SESNSP: https://www.gob.mx/sesnsp/acciones-y-programas/datos-abiertos-de-incidencia-delictiva

## Conjunto de datos

Existen tres fuentes principales sobre incidencia delictiva:

* Estatal: desagregación a nivel entidad federativa.
* **Municipal: Mayor granularidad a nivel municipal.**
* Víctimas: Datos sobre el número de víctimas, con otras variables adicionales como sexo y grupo de edad.

-

### Análisis de Incidencia Delictiva con Microsoft Fabric y Power BI

Este proyecto demuestra un flujo de datos de **end-to-end** para transformar datos públicos de incidencia delictiva en un reporte interactivo y confiable. El objetivo fue convertir datos crudos y dispersos en una **fuente de verdad** para el análisis estratégico, aplicando las mejores prácticas de la ingeniería de datos y la inteligencia de negocios.

-
### Estructura del proyecto

Se aplico una arquitectura **Medallion** implementada en **Microsoft Fabric**. Este enfoque me permitió procesar los datos de manera estructurada y escalable, siguiendo un patrón de **ELT** (Extract, Load, Transform).

* **Bronze 🥉 (Ingesta):** Los datos crudos de incidencia delictiva, obtenidos directamente de SESNSP, se cargaron en esta capa para mantener una copia fiel del origen.
* **Silver 🥈 (Limpieza y Validación):** Aquí se aplicaron transformaciones y reglas de negocio para limpiar y estandarizar la información, asegurando su calidad para el análisis.
* **Gold 🥇 (Análisis):** En esta etapa final, los datos limpios se agregaron y modelaron en un **esquema de estrella (star schema)**, optimizado para el consumo en el reporte de Power BI. Este modelo se compone de una **tabla de hechos** y **tablas de dimensiones** para la exploración de datos.

-
### Resultados y Herramientas

El resultado final se creo un reporte interactivo **Power BI** que ofrece una visión clara y confiable de las tendencias de incidencia delictiva. Para la capa de visualización, se aplicaron principios de **diseño UX (experiencia de usuario)** para asegurar que el reporte sea intuitivo, fácil de navegar y que comunique los insights de manera efectiva a los usuarios finales.

Por razones de costos y practicidad, el modelo semántico se cargó en Fabric y el reporte se desarrolló en **Power BI Desktop**, demostrando un flujo de trabajo realista y eficiente que minimiza los costos computacionales.

* **Tecnologías Clave:** Microsoft Fabric, Power BI.
* **Componentes de Fabric:** Lakehouse, Notebooks de PySpark, Dataflows2
* **Lenguajes:** PySpark, PySQL.
