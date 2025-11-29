# **📘 Capítulo 7 --- Discusión y Conclusiones**

## Sistema de Bicicletas Compartidas -- Bogotá (Dataset `hour`)

## **1. Objetivo General del Proyecto**

Este proyecto tuvo como finalidad construir, analizar y validar un
**modelo de regresión lineal múltiple avanzado** para explicar y
predecir la demanda horaria de bicicletas compartidas (`cnt`).\
Se buscó:

-   Identificar las variables que mejor explican la demanda.
-   Evaluar si el modelo lineal es adecuado para representar el
    fenómeno.
-   Medir el desempeño predictivo mediante validación cruzada.
-   Comparar modelos alternativos y seleccionar el más eficiente.

------------------------------------------------------------------------

## **2. Resumen Metodológico**

### **2.1. Exploración de Datos (EDA)**

Se analizaron patrones fundamentales:

-   Ciclos diarios y semanales.
-   Influencia de variables climáticas.
-   Correlaciones importantes.
-   Presencia de posibles no linealidades.

### **2.2. Preparación del Dataset**

Incluyó:

-   Conversión de variables categóricas a dummies.
-   Limpieza general.
-   Normalización donde fue pertinente.
-   Creación del dataset final apto para modelado.

### **2.3. Ajuste del Modelo Base OLS**

Se construyó un primer modelo completo con todas las variables.\
Allí se detectaron:

-   Multicolinealidad en variables climáticas.
-   Indicios de heterocedasticidad.
-   No linealidad leve.
-   Puntos influyentes.

### **2.4. Diagnóstico del Modelo**

Mediante gráficos:

-   **Residuos vs ajustados:** estructura en los residuos → no
    linealidad.
-   **Q--Q plot:** ligera desviación de normalidad.
-   **Cook's distance:** puntos influyentes naturales (hora 0, 6, 17).
-   **VIF:** correlación moderada entre variables de clima.

### **2.5. Selección de Variables**

Se compararon:

-   Forward Selection (AIC)\
-   Backward Elimination\
-   Stepwise

El método **Forward AIC** fue el ganador por lograr:

-   Modelo corto.
-   Mejor balance entre complejidad y capacidad predictiva.
-   Menor AIC.

### **2.6. Validación Cruzada**

Se aplicó **K-Fold CV (k=5)**.\
Los resultados mostraron:

-   El RMSE de validación es cercano al RMSE de entrenamiento.
-   No hubo sobreajuste importante.
-   El modelo generaliza adecuadamente.

------------------------------------------------------------------------

## **3. Interpretación de Resultados**

### **3.1 Variables más influyentes**

Según el modelo seleccionado, las variables típicamente significativas
son:

-   **Temperatura (`temp`)**\
    Incrementa fuertemente el uso.

-   **Hora del día (`hr`)**\
    Explica picos matutinos y nocturnos.

-   **Día laboral (`workingday`)**\
    Cambia el patrón de movilidad.

-   **Clima (`weathersit`)**\
    Lluvia o clima adverso reduce la demanda.

-   **Humedad y velocidad del viento**\
    Efectos complementarios de menor magnitud.

### **3.2 Bondad del ajuste**

-   R² alto → buena explicación de la variabilidad.
-   RMSE razonable considerando el rango del conteo.
-   Residuals muestran algún nivel de estructura → oportunidades de
    mejora.

------------------------------------------------------------------------

## **4. Limitaciones del Modelo**

-   Relaciones claramente **no lineales** que un modelo OLS básico no
    captura.
-   Persistencia de estructura en residuos.
-   Variabilidad no modelada en horarios muy específicos.
-   Algunas variables correlacionadas entre sí (multicolinealidad
    moderada).

------------------------------------------------------------------------

## **5. Posibles Mejoras Futuras**

### **5.1. Transformaciones**

-   Logaritmos sobre `cnt`.
-   Splines sobre `hr`, `temp`.

### **5.2. Interacciones relevantes**

-   `temp × hr`
-   `workingday × hr`
-   `humidity × weathersit`

### **5.3. Modelos Regularizados**

-   **Ridge** para manejar multicolinealidad.
-   **Lasso** para selección más agresiva.
-   **ElasticNet** para un término híbrido.

### **5.4. Modelos no lineales**

-   Random Forest.
-   Gradient Boosting.
-   Redes neuronales ligeras.

Estos podrían capturar ciclos horarios, estacionalidad semanal y efectos
complejos.

------------------------------------------------------------------------

## **6. Conclusión General**

El proyecto logró:

-   Construir un modelo interpretativo, validado y sustentado.
-   Identificar los determinantes principales de la demanda.
-   Obtener un buen desempeño predictivo.
-   Comprobar la utilidad del modelo para análisis operativo de sistemas
    de bicicletas.

El modelo lineal múltiple es una **excelente base**, pero el fenómeno
real tiene componentes no lineales que motivan futuros modelos más
flexibles.

------------------------------------------------------------------------

✔ **Capítulo finalizado**
