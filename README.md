# Credit_Cards_Analytics

# Análisis de Dataset de Tarjetas de Crédito

Este repositorio contiene el análisis de un dataset de tarjetas de crédito que se puede encontrar en [Kaggle](https://www.kaggle.com/datasets/arjunbhasin2013/ccdata). El análisis se centra en la segmentación de usuarios en dos factores clave: compras y pagos, límite de crédito y saldo en la cuenta, así como adelantos en efectivo. A continuación se detalla la información relevante sobre el proyecto y los hallazgos obtenidos.

## Acerca del Dataset

Este caso requiere desarrollar una segmentación de clientes para definir una estrategia de marketing. El dataset de muestra resume el comportamiento de aproximadamente 9000 titulares de tarjetas de crédito activas durante los últimos 6 meses. El archivo contiene datos a nivel de cliente con 18 variables de comportamiento.

A continuación se muestra el diccionario de datos del dataset de tarjetas de crédito:

- CUST_ID: Identificación del titular de la tarjeta de crédito (Categórica)
- BALANCE: Saldo restante en la cuenta para realizar compras
- BALANCE_FREQUENCY: Frecuencia con la que se actualiza el saldo, puntuación entre 0 y 1 (1 = actualizado con frecuencia, 0 = no actualizado con frecuencia)
- PURCHASES: Monto de compras realizadas desde la cuenta
- ONEOFF_PURCHASES: Monto máximo de compra realizada en una sola transacción
- INSTALLMENTS_PURCHASES: Monto de compra realizado en cuotas
- CASH_ADVANCE: Dinero en efectivo adelantado por el usuario
- PURCHASES_FREQUENCY: Frecuencia con la que se realizan compras, puntuación entre 0 y 1 (1 = compras frecuentes, 0 = compras no frecuentes)
- ONEOFFPURCHASESFREQUENCY: Frecuencia de compras en una sola transacción (1 = compras frecuentes, 0 = compras no frecuentes)
- PURCHASESINSTALLMENTSFREQUENCY: Frecuencia de compras a plazos (1 = frecuentes, 0 = no frecuentes)
- CASHADVANCEFREQUENCY: Frecuencia con la que se paga en efectivo por adelantado
- CASHADVANCETRX: Número de transacciones realizadas con "efectivo adelantado"
- PURCHASES_TRX: Número de transacciones de compra realizadas
- CREDIT_LIMIT: Límite de la tarjeta de crédito para el usuario
- PAYMENTS: Monto de pago realizado por el usuario
- MINIMUM_PAYMENTS: Monto mínimo de pagos realizado por el usuario
- PRCFULLPAYMENT: Porcentaje de pago total realizado por el usuario
- TENURE: Duración del servicio de la tarjeta de crédito para el usuario

## Metodología de Análisis

Para el análisis, se realizó una pequeña limpieza de los datos y se evaluó la correlación entre cada una de las variables. Se llevaron a cabo dos segmentaciones utilizando el método K-means:

1. Segmentación basada en compras, pagos, límite de crédito y saldo en la cuenta.
2. Segmentación basada en adelantos en efectivo, saldo, límite de crédito y pagos.

Posteriormente, se verificó la eficacia de la segmentación mediante la reducción de variables. Finalmente, se creó un dashboard para presentar los gráficos y las conclusiones más importantes.

# Resultados Destacados

## Conclusiones de las correlaciones

![Correlaciones del Dataframe](Documentos_Dashboard\Correlacion.png)


1. La variable 'PURCHASES' muestra una correlación alta con 'ONEOFF_PURCHASES' (0.917), 'INSTALLMENTS_PURCHASES' (0.680), 'PURCHASES_TRX' (0.690) y 'PAYMENTS' (0.603). Esto sugiere que los clientes que realizan compras más grandes (ONEOFF_PURCHASES) tienden a realizar más compras en general (PURCHASES) y en cuotas (INSTALLMENTS_PURCHASES). También hay una relación positiva con los pagos realizados (PAYMENTS), lo que indica que los clientes que realizan más compras también tienden a realizar pagos más grandes.

2. La variable 'CASH_ADVANCE' muestra una correlación significativa con 'CASH_ADVANCE_FREQUENCY' (0.629) y 'CASH_ADVANCE_TRX' (0.656). Esto sugiere que los clientes que hacen más avances de efectivo (CASH_ADVANCE) también tienden a hacerlo con más frecuencia (CASH_ADVANCE_FREQUENCY) y en una mayor cantidad de transacciones (CASH_ADVANCE_TRX).


## Conclsiones de las segmentaciones

Los insights obtenidos a partir del análisis son los siguientes:

![Segmentación de clientes por compras y saldo](Documentos_Dashboard\Segmentación%20para%20los%20clientes%20según%20el%20balance,%20las%20Compras%20y%20el%20máximo%20de%20credito.png)

| Segmentación | Número de clientes | Saldo              | Limite de Credito    | Pagos              | Compras            |
|--------------|--------------------|--------------------|----------------------|--------------------|--------------------|
| 0            | 5370               | 788.6242275523276  | 2163.2161183529083   | 867.0746977486033  | 490.6225288640584  |
| 1            | 867                | 5047.509911416379  | 11822.72727272781   | 3666.0816629665514 | 1954.1553402537484 |
| 2            | 117                | 4608.794345717949  | 12637.606837606836  | 19254.744854358978 | 10800.515811965815 |
| 3            | 2595               | 1869.6335929263971 | 6503.06475156185    | 2090.2271132728324 | 1304.8659922928705 |


- Enfoque en clientes de alto valor: Se recomienda priorizar a los clientes con mayores balances, compras y límites de crédito. Estos clientes son clave para las estrategias de retención y fidelización. Además, la segmentación número 2 destaca por sus altas compras y pagos, aunque no sean numerosos y no tengan los mayores saldos, por lo que también requieren atención especial.




- Captar nuevos clientes potenciales (Oportunidades de crecimiento): La segmentación número 0 representa la mayor cantidad de clientes en el conjunto de datos, lo que indica un gran potencial para captar nuevos clientes. Mejorar su balance es clave para clasificarlos en segmentaciones superiores. Es importante monitorear y analizar su comportamiento, ya que pueden cambiar sus patrones de compra y lealtad.
  
![Segemnatción por adelantos en efectivo](Documentos_Dashboard\Segmentación%20por%20avances%20en%20efectivo.png)

| Segmentación | Número de clientes | % Adelanto en efectivo respecto al pago | Efectivo adelantado | Pagos              | Saldo              | Limite de Credito   |
|--------------|--------------------|---------------------------------------|---------------------|--------------------|--------------------|---------------------|
| 0            | 5399               | 51.15                     | 456.02  | 891.55 | 781.17 | 2170.95  |
| 1            | 112                | 42.57                   | 8455.84  | 19864.79 | 4934.55  | 12486.16 |
| 2            | 2533               | 47.76                      | 982.79   | 2057.52  | 1748.24 | 6635.93   |
| 3            | 905                | 87.71                      | 3164.41  | 3607.81  | 5310.99  | 11387.85  |

- Reducción del pago en efectivo: Las segmentaciones 0 y 3 presentan un alto porcentaje de pagos en efectivo, lo que indica la necesidad de implementar estrategias para disminuir el uso de efectivo y promover los pagos con tarjeta de crédito. Se sugiere establecer programas de incentivos atractivos y programas exclusivos que fomenten la adopción de esta modalidad de pago.

## Referencias

- Modelo de IA: GPT-3.5 de OpenAI


Este modelo de IA, desarrollado por OpenAI, proporciona un soporte avanzado para diversas aplicaciones, incluyendo análisis de datos, generación de texto y procesamiento del lenguaje natural.

Referencia: https://openai.com/

- HAINES CITY Credit Card - PCA - KElbow - KMeans

Este proyecto en Kaggle utiliza técnicas de PCA (Análisis de Componentes Principales), KElbow y KMeans para el análisis de datos de tarjetas de crédito en la ciudad de Haines. Proporciona información valiosa sobre la segmentación de clientes y patrones de comportamiento en los datos de tarjetas de crédito.

Referencia: https://www.kaggle.com/code/hainescity/credit-card-pca-kelbow-kmeans

