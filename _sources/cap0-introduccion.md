# Proyecto Integrador – Regresión Lineal Múltiple Avanzada  
## Sistema de Bicicletas Compartidas (Bike Sharing)

Este proyecto corresponde al desarrollo completo del taller presentado en la sección  
**3.4. Proyecto Integrador: Regresión Lineal Múltiple Avanzada – Sistema de Bicicletas Compartidas**,  
del curso de **Modelos Lineales**. Su objetivo es aplicar de forma integral los conceptos 
teóricos y prácticos de la regresión lineal múltiple sobre un conjunto de datos real 
de movilidad urbana.

---

## 📌 1. Contexto del Sistema de Bicicletas Compartidas

Los sistemas de bicicletas compartidas se han convertido en una alternativa de movilidad 
sostenible y eficiente en ciudades alrededor del mundo. Estos sistemas registran información 
operativa de cada día y hora, como:

- Número de usuarios registrados y casuales  
- Condiciones climáticas  
- Tipo de día (laboral, festivo, fin de semana)  
- Horarios pico  
- Variables de estacionalidad  

Modelar y comprender estos patrones permite:

- Predecir la demanda en distintos horarios  
- Planificar inventarios de bicicletas  
- Optimizar estaciones y redistribuciones  
- Evaluar cómo el clima y factores externos afectan el uso

---

## 📌 2. Descripción del Dataset: `hour.csv`

El conjunto de datos utilizado en este proyecto corresponde al registro horario del sistema 
de bicicletas compartidas. Cada fila representa un período de **1 hora**, incluyendo:

### 🔹 Variables de uso
- **`cnt`**: total de alquileres (variable objetivo del modelo)  
- **`casual`**: usuarios casuales  
- **`registered`**: usuarios registrados  

### 🔹 Variables temporales
- **`hr`**: hora del día  
- **`weekday`**: día de la semana  
- **`workingday`**: indicador de día laboral  
- **`season`**: estación del año  
- **`yr`**: año del registro  

### 🔹 Variables ambientales
- **`temp`**: temperatura normalizada  
- **`atemp`**: sensación térmica  
- **`hum`**: humedad  
- **`windspeed`**: velocidad del viento  
- **`weathersit`**: condición climática general  

En total, el dataset contiene **17 variables** y más de **17,000 observaciones**.

---

## 📌 3. Objetivo del Proyecto

El propósito central es **modelar la demanda horaria de bicicletas (`cnt`)** utilizando diversos 
predictoras climáticas, temporales y operativas, mediante técnicas avanzadas de regresión lineal:

- Regresión lineal múltiple (OLS)  
- Validación cruzada  
- Selección de variables  
- Análisis de supuestos del modelo  
- Regularización (Ridge, Lasso, ElasticNet)  
- Comparación final de modelos y recomendaciones  

---

## 📌 4. Estructura del Taller (Capítulos del Libro)

Este proyecto se organiza en capítulos, siguiendo una progresión lógica desde la exploración de datos 
hasta los métodos avanzados y la interpretación final.

### **Capítulo 0 — Introducción (este documento)**  
Descripción del contexto, dataset y objetivos.

### **Capítulo 1 — Análisis Exploratorio de Datos (EDA)** *(ipynb)*  
Carga del dataset, estadísticas iniciales y visualizaciones clave.

### **Capítulo 2 — Preparación y Limpieza de Datos** *(ipynb)*  
Manejo de valores faltantes, transformación de variables, encoding, escalamiento.

### **Capítulo 3 — Modelo Base OLS** *(ipynb)*  
Ajuste inicial, interpretación de coeficientes y evaluación preliminar.

### **Capítulo 4 — Diagnóstico de Supuestos** *(ipynb)*  
Normalidad, homocedasticidad, linealidad, independencia, leverage, outliers.

### **Capítulo 5 — Selección de Variables y Validación Cruzada** *(ipynb)*  
Creación de modelos candidatos y comparación de desempeño.

### **Capítulo 6 — Regularización Ridge y Lasso** *(ipynb)*  
Penalización L2 y L1, búsqueda de hiperparámetros, análisis de coeficientes.

### **Capítulo 7 — ElasticNet y Comparación Final** *(ipynb)*  
Combinación L1-L2, mejora de estabilidad y tabla final de desempeño.

### **Capítulo 8 — Conclusiones Finales** *(md)*  
Resumen, discusión de resultados y recomendaciones prácticas.

---

## 📌 5. Configuración del Entorno

Todo el análisis se realiza en el entorno virtual:

