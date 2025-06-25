# Challenge_Proceso_ETL: Análisis de abandono y comportamiento del cliente
## Descripción del proyecto
Este proyecto tiene como objetivo analizar los patrones de abandono (churn) y el comportamiento de gasto de los clientes en **Telecom X**. A través del análisis de variables como el total pagado y los meses de contrato, buscamos identificar momentos críticos en la relación con el cliente y proponer estrategias para mejorar la retención y optimizar la oferta de servicios.

## Datos utilizados
El análisis se basó en una base de datos de clientes que incluye, las siguientes métricas clave:
- `customerID`: número de identificación único de cada cliente
- `Churn`: si el cliente dejó o no la empresa
- `gender`: género (masculino y femenino)
- `SeniorCitizen`: información sobre si un cliente tiene o no una edad igual o mayor a 65 años
- `Partner`: si el cliente tiene o no una pareja
- `Dependents`: si el cliente tiene o no dependientes
- `tenure`: meses de contrato del cliente
- `PhoneService`: suscripción al servicio telefónico
- `MultipleLines`: suscripción a más de una línea telefónica
- `InternetService`: suscripción a un proveedor de internet
- `OnlineSecurity`: suscripción adicional de seguridad en línea
- `OnlineBackup`: suscripción adicional de respaldo en línea
- `DeviceProtection`: suscripción adicional de protección del dispositivo
- `TechSupport`: suscripción adicional de soporte técnico, menor tiempo de espera
- `StreamingTV`: suscripción de televisión por cable
- `StreamingMovies`: suscripción de streaming de películas
- `Contract`: tipo de contrato
- `PaperlessBilling`: si el cliente prefiere recibir la factura en línea
- `PaymentMethod`: forma de pago
- `Charges.Monthly`: total de todos los servicios del cliente por mes
- `Charges.Total`: total gastado por el cliente
- `Cuentas_diarias`: Utiliza la Charges.Monthly para calcular el valor diario (tomando meses de 30 días)

## Metodología de análisis
El proyecto siguió un enfoque exploratorio para identificar patrones:

1. **Cálculo de estadísticas descriptivas:** Se calcularon promedios, mínimos, máximos y el Coeficiente de Variación (CV) para las métricas clave, como el gasto mensual, el gasto total acumulado y los meses de contrato.
2. **Análisis de Dispersión:** Se utilizó el Coeficiente de Variación para comprender la heterogeneidad de los datos de gasto.
3. **Visualización de Abandono:** Se crearon gráficos para visualizar la distribución del abandono en función del gasto total, los meses de contrato, entre otros.

## Hallazgos clave
El análisis reveló las siguientes observaciones importantes sobre el comportamiento de los clientes y el abandono:

1. Alta variabilidad en el gasto del cliente: 
    * El gasto mensual de los clientes mostró una variabilidad significativa (CV del 46.5%), con un promedio de $64.7 y un rango de $18.25 a $118.75. Esto indica que los clientes no gastan una cantidad uniforme mes a mes.
    * La variabilidad en el gasto total acumulado es aún más pronunciada (CV del 99.47%). Esto se debe en gran medida a la combinación de la variabilidad del gasto mensual y la alta dispersión en la duración de los contratos de los clientes, lo que sugiere una base de clientes con valores de permanencia muy dispares.

2. Patrones de abandono críticos:
    * El abandono de clientes se concentra en dos períodos clave:
        * Primeros 5 meses: Se observa un volumen considerable de abandonos en las fases iniciales de la relación. Esto sugiere problemas de adaptación, expectativas no cumplidas o falta de valor percibido.
        * Meses avanzados (aproximadamente a partir del mes 60-65 en adelante): Existe un segundo pico de abandono para clientes de muy larga duración. Esto podría estar relacionado con el fin de largos tiempos de contrato, cambios en las necesidades del cliente o la aparición de mejores alternativas en el mercado.
    * Durante los meses intermedios, la tasa de abandono tiende a ser más constante y horizontal, lo que implica una pérdida continua de clientes en cantidades similares cada mes, aunque en menor volumen que en los picos.

3. Aparente relación entre gasto y permanencia:
    * Los clientes que han permanecido por más tiempo son los que, en promedio, han realizado pagos totales más altos, mientras que los clientes de menor duración han realizado menores pagos.
    * En apariencia, esto sugiere que el precio no es el problema principal para la retención de los clientes de largo plazo. Sin embargo, para los clientes que abandonan en las primeras etapas y con menor gasto, el precio podría sí ser un factor que contribuye al abandono. Es crucial recalcar que los datos actuales no son suficientes para concluir si el precio es o no parte del problema principal de manera definitiva.

## Recomendaciones y próximos pasos
Basado en este análisis, se proponen las siguientes recomendaciones estratégicas y necesidades de datos:

1. Recopilación de datos adicionales:
    * Es importante obtener datos con calificaciones directas de los clientes sobre su satisfacción con el servicio, la calidad de los productos, los precios y las condiciones de los tiempos de contrato. Esto permitirá entender el "por qué" detrás de los patrones de abandono observados.

2. Segmentación de servicios y ofertas:
    * Dada la alta variabilidad en el comportamiento del gasto del cliente, se recomienda segmentar la oferta de servicios para satisfacer las diversas necesidades:
        * Servicios básicos o planes de entrada: Diseñados para atraer nuevos clientes y demostrar el valor y la calidad del producto, con el objetivo de reducir el churn temprano.
        * Planes premium o de alto volumen de consumo: Dirigidos a clientes cuyas necesidades exceden los planes básicos, fomentando el mayor gasto y la retención a largo plazo.
        * Modelos de precios y características flexibles: Ofrecer opciones con tarifas y características fijas, así como planes basados en el consumo, para adaptarse a las diversas preferencias de los clientes.

## Análisis de mercado y feedback continuo:
Implementar un análisis de mercado y establecer mecanismos continuos para recopilar reseñas y feedback de los clientes. Esto ayudará a comprender mejor las expectativas de los diferentes segmentos de clientes y a identificar oportunidades para la mejora del servicio.

## Tecnologías/Herramientas utilizadas
[Python en Jupyter Notebooks]
[Librerías de análisis de datos, Pandas, NumPy]
[Librerías de visualización, Matplotlib, Seaborn]

## Estructura del repositorio
.
├── Challenge_telecom.ipynb    <- Cuaderno Jupyter con el análisis principal (incluye ETL, análisis y visualizaciones)
├── README.md                  <- Este archivo
├── TelecomX_Data.json         <- Archivo de datos en formato JSON utilizado para el análisis
└── TelecomX_diccionario.md    <- Diccionario de datos o archivo de metadatos de las columnas