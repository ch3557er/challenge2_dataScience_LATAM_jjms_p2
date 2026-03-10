<h1 align="center">📡 Telecom X LATAM — Predicción de Cancelación de Clientes 📡</h1>
<h1 align="center">(Challenge 2 — Fase 2: Machine Learning)</h1>

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.12.0-blue?style=for-the-badge&logo=python&logoColor=white"/>
  <img src="https://img.shields.io/badge/Pandas-2.2.2-150458?style=for-the-badge&logo=pandas&logoColor=white"/>
  <img src="https://img.shields.io/badge/Scikit--Learn-1.x-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white"/>
  <img src="https://img.shields.io/badge/XGBoost-2.x-FF6600?style=for-the-badge&logo=xgboost&logoColor=white"/>
  <img src="https://img.shields.io/badge/STATUS-FINALIZADO-green?style=for-the-badge"/>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Jupyter-Notebook-F37626?style=flat-square&logo=jupyter&logoColor=white"/>
  <img src="https://img.shields.io/badge/Google%20Colab-F9AB00?style=flat-square&logo=googlecolab&logoColor=white"/>
</p>

---

## 📋 Índice

- [Descripción del Proyecto](#-descripción-del-proyecto)
- [Contexto — Fase 1 y Fase 2](#-contexto--fase-1-y-fase-2)
- [El Desafío](#-el-desafío)
- [Pipeline del Proyecto](#-pipeline-del-proyecto)
- [Tecnologías Utilizadas](#️-tecnologías-utilizadas)
- [Resultados Clave](#-resultados-clave)
- [Comparativa de Modelos](#-comparativa-de-modelos)
- [Variables Más Importantes](#-variables-más-importantes)
- [Cómo Ejecutar el Proyecto](#-cómo-ejecutar-el-proyecto)
- [Estructura del Proyecto](#-estructura-del-proyecto)
- [Conclusión Final](#-conclusión-final)
- [Desarrollador](#desarrollador)

---

## 🎯 Descripción del Proyecto

Este proyecto es la **continuación directa del análisis exploratorio de la Fase 1** de Telecom X. Mientras que en la Fase 1 se identificaron los factores de cancelación mediante EDA, en esta **Fase 2** se construye un **pipeline completo de Machine Learning** para **predecir qué clientes tienen mayor probabilidad de cancelar** su servicio.

El objetivo es pasar del análisis descriptivo ("¿quién cancela?") al análisis predictivo ("¿quién va a cancelar?"), entregando un modelo listo para producción que permita al área comercial actuar de forma proactiva sobre los clientes en riesgo.

### 💡 Objetivo Principal
Desarrollar y evaluar modelos de clasificación para predecir el **churn de clientes**, identificar las variables más influyentes y proponer estrategias de retención respaldadas en los datos.

---

## 🔗 Contexto — Fase 1 y Fase 2

| | Fase 1 — EDA | Fase 2 — Machine Learning |
|---|---|---|
| **Pregunta** | ¿Quién cancela y por qué? | ¿Quién va a cancelar? |
| **Enfoque** | Análisis exploratorio | Modelado predictivo |
| **Entregable** | Informe + visualizaciones | Modelos entrenados + score de riesgo |
| **Dataset** | JSON desde API pública | CSV tratado de la Fase 1 |

> 📌 Este proyecto usa como input el archivo `datos_tratados.csv` generado en la Fase 1.

---

## 🚀 El Desafío

**Practicando Python para Data Science: Challenge 2 — TelecomX (Fase 2)**  
*Especialización en Data Science - Alura LATAM*

El desafío consistió en:
- ✅ Preparar los datos para modelado (encoding, estandarización, balanceo)
- ✅ Realizar análisis de correlación y selección de variables con **Chi-cuadrado**
- ✅ Entrenar **4 modelos de clasificación** de dos familias distintas
- ✅ Evaluar modelos con métricas: Accuracy, Precision, Recall, F1, Matriz de Confusión
- ✅ Analizar la **importancia de variables** por modelo
- ✅ Elaborar una **conclusión estratégica** con recomendaciones de retención

---

## 🔍 Pipeline del Proyecto

El proyecto está organizado en **7 capítulos** con secuencia lógica de ML:

### 1️⃣ **Cap 1 — Recolección**
- Carga del `datos_tratados.csv` generado en la Fase 1
- Verificación de estructura: 7,043 registros, 22 columnas

### 2️⃣ **Cap 2 — EDA (Análisis Exploratorio)**
- Verificación de proporción de churn: **73.5% No / 26.5% Yes**
- Matriz de correlación entre variables numéricas
- Boxplots de `Tenure`, `ChargesMonthly` y `ChargesTotal` vs Churn
- Análisis de variables categóricas (crosstab por tasa de churn)
- **Chi-cuadrado**: ranking estadístico de importancia de variables categóricas

### 3️⃣ **Cap 3 — Pre-procesamiento**
- Eliminación de columnas irrelevantes (`CustomerID`, `Gender`, `PhoneService`, `ChargesDaily`, `ChargesTotal`)
- Unificación de categorías redundantes ("No internet service" → "No")
- Verificación de nulos post-limpieza
- Mapeo de variable objetivo: `Churn` → 0/1

### 4️⃣ **Cap 4 — Split + Encoding + Estandarización**
- División estratificada: **80% train / 20% test**
- One-Hot Encoding **después del split** (evita data leakage)
- `StandardScaler` solo en variables numéricas (`Tenure`, `ChargesMonthly`)

### 5️⃣ **Cap 5 — Entrenamiento**
- Modelo 1: Regresión Logística estándar
- Modelo 2: Regresión Logística con `class_weight="balanced"`
- Modelo 3: Random Forest
- Modelo 4: XGBoost con `scale_pos_weight=2.77`

### 6️⃣ **Cap 6 — Evaluación**
- Classification reports para los 4 modelos
- Matrices de confusión
- Análisis comparativo con tabla de métricas

### 7️⃣ **Cap 7 — Interpretación y Conclusiones**
- Coeficientes de Regresión Logística (gráfico bicolor)
- Importancia de variables: Random Forest y XGBoost
- Informe final con factores clave y estrategias de retención

---

## 🛠️ Tecnologías Utilizadas

| Tecnología | Versión | Uso en el Proyecto |
|------------|---------|-------------------|
| **Python** | 3.12.0 | Lenguaje principal |
| **Pandas** | 2.2.2 | Manipulación y análisis de datos |
| **Scikit-Learn** | 1.x | Modelos, métricas, preprocesamiento |
| **XGBoost** | 2.x | Modelo de boosting para clasificación |
| **Matplotlib** | 3.10.0 | Visualizaciones estáticas |
| **Seaborn** | 0.13.2 | Heatmaps y boxplots |
| **Jupyter Notebook** | .ipynb | Formato del proyecto |
| **Google Colab** | — | Entorno de desarrollo |

---

## 📊 Resultados Clave

### 📉 Desbalance de Clases
| Estado | Clientes | Porcentaje |
|--------|----------|------------|
| **Permanecen** | ~5,174 | 73.5% ✅ |
| **Cancelaron (Churn)** | ~1,869 | 26.5% 🔴 |
| **Total** | ~7,043 | 100% |

> **Desbalance moderado** — manejado con `class_weight="balanced"` en Regresión Logística y `scale_pos_weight=2.77` en XGBoost.

---

## 🤖 Comparativa de Modelos

| Modelo | Accuracy | Precision (Yes) | Recall (Yes) | F1 (Yes) |
|--------|----------|-----------------|--------------|----------|
| Reg. Logística (estándar) | 0.80 | 0.65 | 0.52 | 0.58 |
| **Reg. Logística (balanceada)** | **0.74** | **0.51** | **0.79** | **0.62** |
| Random Forest | 0.79 | 0.63 | 0.48 | 0.55 |
| XGBoost | 0.75 | 0.52 | 0.68 | 0.59 |

> 🏆 **Mejor modelo: Regresión Logística Balanceada**  
> Recall (Yes) = **0.79** → detecta correctamente 8 de cada 10 clientes que cancelarán.  
> En churn, el error más costoso es **no detectar** a un cliente en riesgo.

### Lectura de Matrices de Confusión
| Modelo | Churns detectados | Churns escapados |
|--------|-------------------|-----------------|
| Reg. Logística estándar | 196 | 178 |
| **Reg. Logística balanceada** | **296** | **78** |
| Random Forest | 181 | 193 |
| XGBoost | 253 | 121 |

---

## 📈 Variables Más Importantes

Los tres modelos coinciden en los mismos factores de riesgo:

| Factor de riesgo | Reg. Logística | Random Forest | XGBoost |
|-----------------|:--------------:|:-------------:|:-------:|
| Fiber optic | ⭐⭐⭐ Muy alto | ⭐⭐ Alto | ⭐⭐⭐ Muy alto |
| Contrato mensual | ⭐⭐⭐ Muy alto | ⭐⭐ Alto | ⭐⭐⭐ Muy alto |
| Electronic check | ⭐⭐ Alto | ⭐⭐ Alto | ⭐ Moderado |
| Tenure bajo | ⭐⭐ Alto | ⭐⭐⭐ Muy alto | ⭐ Bajo |
| ChargesMonthly | 🔵 Protector (multivariado) | ⭐⭐⭐ Muy alto | ⭐ Bajo |

**Diferencia entre modelos:**
- **Random Forest** prioriza variables continuas: `ChargesMonthly` y `Tenure` (~0.25 c/u)
- **XGBoost** concentra el peso en el tipo de contrato: `Contract_Two year` (~0.37)
- **Reg. Logística** muestra dirección: `InternetService_Fiber optic` empuja a cancelar (~1.3), `Contract_Two year` protege (~-1.4)

---

## 💻 Cómo Ejecutar el Proyecto

### Prerequisito
Este proyecto requiere el archivo `datos_tratados.csv` generado en la **Fase 1**.  
👉 [Ver repositorio Fase 1](https://github.com/ch3557er/challenge2_dataScience_LATAM_jjms)

### Opción 1: Google Colab (Recomendado)
```bash
1. Descarga TelecomX_2_LATAM_jjmsV1.ipynb y datos_tratados.csv (incluidos en este repo)
2. Abre Google Colab (https://colab.research.google.com/)
3. Carga el notebook: Archivo > Subir notebook
4. Opción A: sube datos_tratados.csv a /content/ y usa la línea comentada del notebook
   Opción B: sube a Google Drive y usa la ruta de Drive (celda activa por defecto)
5. Ejecuta todo: Entorno de ejecución > Ejecutar todo
```

### Opción 2: Visual Studio Code
```bash
# 1. Clonar el repositorio
git clone <tu-repositorio>
cd challenge2_dataScience_LATAM_jjms_p2

# 2. Instalar dependencias
pip install pandas scikit-learn xgboost matplotlib seaborn jupyter

# 3. Abrir el archivo
code TelecomX_2_LATAM_jjmsV1.ipynb

# 4. En la celda de carga, activar la línea comentada:
#    df = pd.read_csv('datos_tratados.csv')
# 5. Ejecutar con Shift + Enter (o "Run All")
```

### Opción 3: Jupyter Notebook local
```bash
pip install pandas scikit-learn xgboost matplotlib seaborn jupyter
jupyter notebook TelecomX_2_LATAM_jjms.ipynb
```

---

## 📁 Estructura del Proyecto

```
challenge2_dataScience_LATAM_jjms_p2/
│
├── TelecomX_2_LATAM_jjms.ipynb  # Notebook principal — pipeline ML completo
├── datos_tratados.csv              # Dataset de entrada (incluido en el repositorio)
└── README.md                       # Documentación del proyecto
```

### Estructura Interna del Notebook
| Cap | Etapa | Contenido |
|-----|-------|-----------|
| Cap 1 | Recolección | Carga del CSV + librerías |
| Cap 2 | EDA | Correlación, boxplots, crosstab, Chi-cuadrado |
| Cap 3 | Pre-procesamiento | Drop columnas, fix categorías, mapeo Churn |
| Cap 4 | Split | Train/test + One-Hot Encoding + StandardScaler |
| Cap 5 | Entrenamiento | 4 modelos (2 familias distintas) |
| Cap 6 | Evaluación | Reports + matrices + análisis comparativo |
| Cap 7 | Interpretación | Importancia de variables + conclusión estratégica |

---

## 🎓 Conclusión Final

### ➡️ Perfil del Cliente en Mayor Riesgo de Cancelar

> *Cliente nuevo, con contrato mes a mes, servicio de Fiber optic, que paga con cheque electrónico y cargo mensual elevado.*

**🔴 Factores que más empujan a cancelar:**
1. **Contrato mensual** → sin compromiso de permanencia, se va ante cualquier insatisfacción (~43% churn)
2. **Fiber optic** → mayor tasa de insatisfacción (~42% churn), posible brecha precio-calidad
3. **Tenure bajo** → mediana de ~10 meses entre quienes cancelan vs ~38 meses entre quienes se quedan
4. **Electronic check** → método de pago con mayor tasa de cancelación (~45%)
5. **Sin TechSupport / OnlineSecurity** → sin servicios adicionales, menor valor percibido (~31% churn)

**🟢 Factores protectores (cliente fiel):**
- Contrato de 2 años → coeficiente ~-1.4 (barrera más fuerte contra el churn)
- Sin servicio de internet → tasa de churn apenas 7%
- Con soporte técnico y seguridad online activos

### 📌 Estrategias de Retención Recomendadas

| # | Estrategia | Variable de Apoyo |
|---|------------|-------------------|
| 1 | **Migrar clientes a contratos anuales/bianuales** con descuentos en los primeros 3 meses | Tipo de contrato |
| 2 | **Programa de bienvenida** con seguimiento en meses 3, 6 y 9 | Tenure |
| 3 | **Auditar urgentemente Fiber optic**: precio vs. calidad percibida | Tipo de internet |
| 4 | **Ofrecer prueba gratuita de TechSupport y OnlineSecurity** (3 meses) | Servicios adicionales |
| 5 | **Incentivar migración desde Electronic check** a pago automático (~16% churn) | Método de pago |

---

## Desarrollador

**Jhonatan Jhonsson Mendoza Sulcaray**  
Email: chessterdev@gmail.com  
LinkedIn: https://linkedin.com/in/chessterdev  
GitHub: https://github.com/ch3557er

---

<p align="center">
  <img src="https://img.shields.io/badge/Proyecto-Challenge%202%20Alura%20LATAM-orange?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Fase-2%20%E2%80%94%20Machine%20Learning-purple?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Fecha-Marzo%202026-blue?style=for-the-badge"/>
</p>

<p align="center">
  ⭐ Si este proyecto te fue útil, considera darle una estrella ⭐
</p>

<p align="center">
  Hecho con 💙 y ☕ para Alura LATAM
</p>
