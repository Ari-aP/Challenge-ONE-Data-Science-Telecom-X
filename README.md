# 📊 Telecom X — Análisis de Evasión de Clientes (Churn)

![Python](https://img.shields.io/badge/Python-3.10-blue)
![Pandas](https://img.shields.io/badge/Pandas-Análisis%20de%20Datos-orange)
![Matplotlib](https://img.shields.io/badge/Matplotlib-Visualización-green)
![Seaborn](https://img.shields.io/badge/Seaborn-EDA-red)
![Estado](https://img.shields.io/badge/Proyecto-Completado-brightgreen)

---

# 📌 Descripción del proyecto

La evasión de clientes (**Customer Churn**) representa uno de los principales desafíos para las empresas de telecomunicaciones. Cuando un cliente cancela el servicio, la empresa pierde ingresos recurrentes y debe invertir recursos adicionales en la adquisición de nuevos clientes.

En este proyecto se analizan los datos de clientes de **Telecom X** con el objetivo de identificar patrones asociados con la cancelación del servicio. A través de procesos de **limpieza, transformación y análisis exploratorio de datos (EDA)**, se busca comprender los factores que influyen en la evasión y generar insights que permitan mejorar las estrategias de retención de clientes.

---

# 🎯 Objetivo del análisis

El objetivo principal del análisis es:

- Comprender la **distribución de la evasión de clientes**.
- Identificar **variables asociadas al churn**.
- Detectar patrones en el comportamiento de los clientes que cancelan el servicio.
- Generar **recomendaciones basadas en datos** para mejorar la retención de clientes.

---

# 🧰 Tecnologías utilizadas

Este proyecto fue desarrollado utilizando:

- **Python**
- **Pandas** → manipulación y análisis de datos
- **Matplotlib** → visualización de datos
- **Seaborn** → análisis exploratorio de datos
- **Jupyter Notebook / Google Colab**

---

# 📂 Estructura del proyecto

```
TelecomX-Churn-Analysis
│
├── TelecomX_LATAM.ipynb
│   Notebook principal que contiene:
│   • Extracción de datos desde API
│   • Transformación de datos (ETL)
│   • Limpieza de datos
│   • Análisis exploratorio de datos (EDA)
│   • Visualizaciones
│   • Insights y recomendaciones
│
└── README.md
    Documentación del proyecto
```

---

# 🔄 Flujo del análisis de datos

El proyecto sigue un flujo típico de análisis de datos.

## 1️⃣ Extracción de datos

Los datos fueron obtenidos desde una **API en formato JSON** y cargados en un DataFrame utilizando la librería **Pandas**.

```python
import pandas as pd

url = "https://raw.githubusercontent.com/ingridcristh/challenge2-data-science-LATAM/main/TelecomX_Data.json"

df = pd.read_json(url)
df.head()
```

---

## 2️⃣ Transformación de datos

Debido a que el dataset contenía estructuras anidadas, se realizó un proceso de **normalización de columnas** para convertir los datos en un formato tabular adecuado para el análisis.

Esto permitió separar la información de cliente, servicios y cuenta en columnas independientes dentro del DataFrame.

---

## 3️⃣ Limpieza de datos

Durante esta etapa se realizaron los siguientes procesos:

- verificación de valores nulos
- detección de registros duplicados
- estandarización de variables categóricas
- conversión de variables numéricas al tipo de dato adecuado

Ejemplo de verificación de valores nulos:

```python
df_final.isnull().sum()
```

---

## 4️⃣ Ingeniería de variables

Se creó una nueva variable llamada **Cuentas_Diarias**, calculada a partir de los cargos mensuales.

```python
df_final["Cuentas_Diarias"] = df_final["Charges.Monthly"] / 30
```

Esta variable permite analizar el comportamiento de gasto de los clientes con mayor precisión.

---

# 📊 Análisis exploratorio de datos (EDA)

Se realizaron diferentes análisis para identificar patrones asociados a la evasión de clientes.

## Distribución de evasión

Se analizó la proporción de clientes que permanecen en la empresa frente a aquellos que cancelan el servicio.

## Evasión según variables categóricas

Se exploraron variables como:

- género
- tipo de contrato
- servicio de internet
- método de pago
- condición de cliente senior

Estas visualizaciones permitieron identificar qué segmentos presentan mayor probabilidad de cancelar el servicio.

## Evasión según variables numéricas

También se analizaron variables como:

- **tenure** (tiempo que el cliente lleva en la empresa)
- **Charges.Monthly** (cargos mensuales)
- **Charges.Total** (gasto total del cliente)
- **Cuentas_Diarias** (gasto promedio diario)

Este análisis permitió identificar diferencias entre clientes que permanecen y aquellos que cancelan el servicio.

---

# 📈 Principales insights

A partir del análisis se identificaron varios patrones relevantes:

- Los clientes con **contratos mensuales (Month-to-month)** presentan mayor tasa de evasión.
- Los clientes con **menor tiempo de permanencia en la empresa** tienen mayor probabilidad de cancelar el servicio.
- Los clientes con **cargos mensuales más altos** muestran mayor tendencia a abandonar el servicio.
- Los clientes que utilizan **Electronic Check** como método de pago presentan mayores niveles de evasión.
- Los contratos de **mayor duración (1 o 2 años)** están asociados con una mayor retención de clientes.

---

# 💡 Recomendaciones estratégicas

Con base en los resultados obtenidos, se proponen las siguientes estrategias:

### Incentivar contratos de largo plazo

Ofrecer promociones o descuentos a clientes que opten por contratos de **uno o dos años**, lo que podría reducir significativamente la evasión.

### Mejorar la experiencia en los primeros meses

Dado que la evasión es mayor en clientes con bajo **tenure**, es recomendable implementar estrategias de acompañamiento para nuevos clientes.

### Revisar la estructura de precios

Analizar los planes con **cargos mensuales más elevados** para mejorar la percepción de valor del servicio.

### Promover métodos de pago automáticos

Incentivar métodos de pago automáticos, como tarjetas o transferencias bancarias, ya que presentan menor evasión.

---

# ▶️ Cómo ejecutar el proyecto

1️⃣ Clonar el repositorio

```bash
git clone https://github.com/Ari-aP/Challenge-ONE-Data-Science-Telecom-X
```

2️⃣ Abrir el notebook en **Jupyter Notebook o Google Colab**

3️⃣ Ejecutar las celdas en orden para reproducir el análisis completo.

---

# 📊 Dataset

El dataset contiene información sobre clientes de Telecom X, incluyendo:

- datos demográficos
- servicios contratados
- tipo de contrato
- método de pago
- cargos mensuales y totales
- estado de evasión del cliente

Los datos fueron obtenidos desde una **API en formato JSON**.

---

# 👩‍💻 Autor

Proyecto desarrollado por Ariadne Arambulo.

---

# ⭐ Conclusión

Este proyecto demuestra cómo aplicar técnicas de **limpieza de datos, análisis exploratorio y visualización** para identificar patrones relevantes en el comportamiento de los clientes y generar **insights accionables para la toma de decisiones estratégicas**.
