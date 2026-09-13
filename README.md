# 🚢 Titanic - Machine Learning con Python

Proyecto de **Machine Learning** desarrollado en Python utilizando un conjunto de datos del Titanic.

El objetivo es entrenar un modelo capaz de **predecir si un pasajero habría sobrevivido o no** utilizando diferentes características, como su género, clase, edad y composición familiar.

---

## 🎯 Objetivo del proyecto

Este proyecto fue realizado como una práctica para aprender los conceptos fundamentales de **Machine Learning con Python**.

El modelo analiza los patrones presentes en los datos históricos de los pasajeros del Titanic y utiliza esos patrones para realizar predicciones sobre pasajeros nuevos.

Entre las variables utilizadas se encuentran:

* Clase del pasajero
* Género
* Edad
* Hermanos o cónyuges a bordo
* Padres o hijos a bordo

---

## 🧠 Modelo utilizado

Para realizar las predicciones se utilizó un:

**Decision Tree Classifier (Árbol de Decisión)**

El árbol de decisión aprende diferentes patrones a partir de los datos de entrenamiento y crea una serie de decisiones para clasificar a los pasajeros.

Por ejemplo, el modelo puede aprender que determinadas combinaciones de características tienen una mayor relación con la supervivencia.

---

## 🔬 Proceso de Machine Learning

El proyecto sigue el siguiente flujo:

```text
Datos del Titanic
       ↓
Carga de los datos
       ↓
Preparación de los datos
       ↓
Separación de X e y
       ↓
Train / Test Split
       ↓
Creación del Decision Tree
       ↓
Entrenamiento del modelo
       ↓
Predicciones
       ↓
Evaluación
       ↓
Matriz de confusión
       ↓
Visualización del árbol
       ↓
Predicción de nuevos pasajeros
```

---

## 🛠️ Tecnologías utilizadas

* **Python**
* **Pandas**
* **Matplotlib**
* **Scikit-learn**
* **Jupyter Notebook**

### Librerías principales

```python
import pandas as pd
import matplotlib.pyplot as plt

from sklearn.model_selection import train_test_split
from sklearn.tree import DecisionTreeClassifier, plot_tree
from sklearn.metrics import accuracy_score, confusion_matrix, ConfusionMatrixDisplay
```

---

## 📊 Preparación de los datos

Antes de entrenar el modelo, los datos deben prepararse para que puedan ser utilizados por Machine Learning.

Por ejemplo, la variable `genero` originalmente contiene valores de texto.

Se transforma a valores numéricos:

```text
hombre → 0
mujer  → 1
```

Esto permite que el modelo pueda utilizar esta información durante el entrenamiento.

---

## 🧪 Entrenamiento y prueba

Los datos se dividen en dos grupos:

* **80% → datos de entrenamiento**
* **20% → datos de prueba**

```python
X_train, X_test, y_train, y_test = train_test_split(
    X,
    y,
    test_size=0.2,
    random_state=42
)
```

Los datos de entrenamiento permiten que el modelo aprenda los patrones.

Los datos de prueba se mantienen separados para comprobar posteriormente qué tan bien funciona el modelo con datos que no utilizó durante el entrenamiento.

---

## 🌳 Árbol de decisión

El modelo utilizado es:

```python
DecisionTreeClassifier(
    max_depth=3,
    random_state=42
)
```

Se utiliza `max_depth=3` para limitar la profundidad del árbol y evitar que se vuelva excesivamente complejo.

También se utiliza `random_state=42` para obtener resultados reproducibles.

---

## 📈 Evaluación del modelo

Para evaluar el modelo se utiliza `accuracy_score`.

Esta métrica permite conocer la proporción de predicciones que fueron correctas.

También se utiliza una **matriz de confusión**:

```python
ConfusionMatrixDisplay.from_predictions(
    y_test,
    predicciones
)
```

La matriz de confusión permite comparar:

```text
y_test
↓
Resultado real

vs.

predicciones
↓
Resultado que calculó el modelo
```

De esta manera podemos observar los aciertos y errores del modelo.

---

## 🌳 Visualización del árbol

El árbol entrenado también se representa gráficamente:

```python
plot_tree(
    arbol,
    feature_names=X.columns,
    class_names=["murio", "sobrevivio"],
    filled=True
)
```

Esto permite observar visualmente las decisiones que el modelo aprendió a utilizar para clasificar a los pasajeros.

---

## 🔎 Importancia de las variables

También se analiza qué características tuvieron mayor importancia dentro del árbol:

```python
arbol.feature_importances_
```

Esto permite conocer qué variables tuvieron mayor influencia en las decisiones tomadas por el modelo.

---

## 👤 Predicción de Jack y Rose

Como parte final del proyecto, utilizamos el modelo entrenado para realizar predicciones sobre dos pasajeros nuevos:

### Jack

```text
Clase: 3
Género: Hombre
Edad: 20
Hermanos/Cónyuges: 0
Padres/Hijos: 0
```

### Rose

```text
Clase: 1
Género: Mujer
Edad: 17
Hermanos/Cónyuges: 1
Padres/Hijos: 1
```

El modelo utiliza estas características para realizar una predicción.

### Resultado

Según el modelo:

* **Jack → probablemente no habría sobrevivido.**
* **Rose → probablemente sí habría sobrevivido.**

> ⚠️ Estas conclusiones son predicciones realizadas por un modelo de Machine Learning a partir de los datos disponibles. No representan una certeza histórica sobre lo que habría ocurrido realmente.

---

## 📚 Lo que aprendí

Durante este proyecto practiqué conceptos fundamentales de Machine Learning:

* Carga y manipulación de datos con **Pandas**.
* Preparación y transformación de datos.
* Separación de variables predictoras (`X`) y objetivo (`y`).
* División de datos con `train_test_split`.
* Entrenamiento de modelos.
* Uso de `DecisionTreeClassifier`.
* Predicciones utilizando `.predict()`.
* Evaluación mediante `accuracy_score`.
* Matrices de confusión.
* Visualización de árboles de decisión.
* Importancia de características.
* Conceptos básicos de **overfitting** y **underfitting**.
* Predicción sobre datos nuevos.

---

## 📁 Archivos del proyecto

```text
Titanic-Machine-Learning/
│
├── Titanic_Machine_Learning_Comentado.ipynb
├── titanic.csv
└── README.md
```

El archivo `.ipynb` contiene el código, los resultados y explicaciones detalladas de cada etapa del proyecto.

---

## 🚀 Cómo ejecutar el proyecto

### 1. Clonar el repositorio

```bash
git clone URL_DEL_REPOSITORIO
```

### 2. Entrar en la carpeta

```bash
cd Titanic-Machine-Learning
```

### 3. Instalar las dependencias

```bash
pip install pandas matplotlib scikit-learn jupyter
```

### 4. Abrir Jupyter Notebook

```bash
jupyter notebook
```

Después abre:

```text
Titanic_Machine_Learning_Comentado.ipynb
```

y ejecuta las celdas en orden.

---

## 👨‍💻 Proyecto de aprendizaje

Este proyecto forma parte de mi aprendizaje de **Python y Machine Learning**.

El objetivo principal no fue solamente crear un modelo, sino comprender **qué hace cada línea de código y cómo funciona el proceso completo de Machine Learning**, desde la preparación de los datos hasta la realización de nuevas predicciones.
