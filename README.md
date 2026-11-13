# Clasificación de la biodegradabilidad de sustancias químicas mediante Machine Learning

## Descripción

La biodegradabilidad es la capacidad de una sustancia para transformarse por la actividad de microorganismos. Estudiarla ayuda a comprender su posible comportamiento ambiental. Este proyecto académico compara modelos que predicen si una sustancia es fácilmente biodegradable a partir de sus características moleculares.

## Dataset

Los datos provienen de UCI Machine Learning Repository. El archivo original contiene 1,055 observaciones y 41 descriptores moleculares. Tras eliminar tres duplicados exactos, se utilizan 1,052 observaciones, sin valores faltantes. Las clases son RB (fácilmente biodegradable) y NRB (no clasificada como fácilmente biodegradable); NRB no significa que nunca pueda biodegradarse.

## Modelos utilizados

Se comparan Regresión Logística, KNN, SVM, Gaussian Naive Bayes y Random Forest. Un DummyClassifier sirve como referencia ingenua separada.

## Resultados

SVM fue seleccionado por su F1 medio de RB en validación cruzada de entrenamiento (0.8211), prácticamente empatado con Regresión Logística (0.8205), sin demostrar superioridad estadística concluyente. En prueba, SVM obtuvo accuracy de 0.8531 y F1 de 0.7770; Random Forest alcanzó un F1 mayor (0.8235), pero ese resultado no cambia la selección previa. El desbalance de clases y la posible semejanza química entre entrenamiento y prueba limitan las conclusiones a una evaluación interna, sin garantizar resultados en familias químicas nuevas ni sustituir ensayos experimentales.

## Cómo ejecutar el proyecto

1. Desde la raíz del proyecto, activa `.venv` e instala las dependencias:

   ```bash
   python -m pip install pandas numpy matplotlib scikit-learn ipykernel notebook
   ```

2. Abre `analisis_biodegradabilidad.ipynb` en PyCharm o Jupyter y selecciona el intérprete de `.venv`.
3. Conserva el CSV en `data/raw/biodeg.csv` y ejecuta las celdas en orden, desde el principio.

## Fuente de los datos

[QSAR biodegradation — UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/254/qsar+biodegradation)
