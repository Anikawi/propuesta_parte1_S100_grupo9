# Riesgo postcompra de vehículos nuevos en Panamá

Proyecto desarrollado para la materia **S100 - Introducción a la Ciencia de Datos** de la Maestría en Analítica de Datos de la Universidad Tecnológica de Panamá.

## Sobre el proyecto

La idea del proyecto nace de una pregunta sencilla:

**¿Una marca que tiene más reclamaciones necesariamente representa un mayor riesgo postcompra?**

No necesariamente, porque una marca que vende muchos más vehículos también puede recibir una mayor cantidad de reclamaciones.

Por esta razón combinamos información de **reclamaciones de consumidores de ACODECO** con información de **ventas de vehículos nuevos de ADAP**, buscando comparar las marcas de una forma más justa.

El análisis trabaja con las reclamaciones registradas durante **2024 y 2025**.

## Datos utilizados

Utilizamos dos fuentes principales:

- **ACODECO:** reclamaciones relacionadas con vehículos.
- **ADAP:** ventas de vehículos nuevos por marca para 2024 y 2025.

Después del proceso de limpieza, revisión de marcas e integración de ambas fuentes, obtuvimos **44 combinaciones marca-año** que forman el conjunto utilizado para el análisis y las primeras pruebas de modelos.

## Cómo medimos el riesgo

Para comparar marcas de diferentes tamaños calculamos:

**Reclamaciones por cada 1,000 vehículos vendidos**

A partir de este indicador organizamos las observaciones en tres niveles de riesgo relativo:

- Bajo
- Medio
- Alto

Estos niveles representan una comparación dentro de los datos analizados y no una clasificación oficial de las marcas.

También encontramos que el tamaño de la marca influye en este indicador. Cuando una marca tiene pocas ventas, unas pocas reclamaciones pueden aumentar bastante la tasa, por lo que este resultado debe interpretarse con cuidado.

## Modelado

Como primera aproximación estamos comparando modelos sencillos de clasificación:

- Regresión Logística
- Árbol de Decisión
- Una referencia básica para comparar resultados

Debido a que algunas marcas aparecen tanto en 2024 como en 2025, también probamos diferentes formas de validación para evitar que una misma marca quede al mismo tiempo en entrenamiento y evaluación.

Actualmente los resultados muestran que existe cierta señal en las variables utilizadas, pero con **44 observaciones todavía no es posible afirmar que un modelo sea claramente mejor que otro**.

Por ahora el objetivo es entender bien los datos, validar correctamente los modelos y documentar las limitaciones antes de avanzar a una versión final.

## Estructura del repositorio

```text
propuesta_parte1_S100_grupo9/
│
├── README.md
├── S100_E9.ipynb
│
└── datos/
    ├── decision-de-quejas-2024.csv
    ├── decisionquejas_2025.csv
    └── ADAP_Ventas_Marcas_2025.csv
```
El notebook principal es:

S100_E9.ipynb

En él se encuentra todo el proceso desde la exploración inicial, limpieza e integración de los datos hasta las primeras pruebas de entrenamiento y validación.

Equipo 9

Ana Aguilar
Jesus Gonzalez
Felix Villa

Universidad Tecnológica de Panamá
Maestría en Analítica de Datos

    
