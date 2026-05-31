# TFM-Posicionamiento-WiFi-CNN
Código fuente del Trabajo Final de Máster - Máster en Ciencia de Datos (UOC)

# Posicionamiento Wi-Fi en Interiores mediante Arquitecturas CNN Jerárquicas y de Regresión

Este repositorio contiene el código fuente, los entornos de desarrollo y los notebooks interactivos correspondientes al **Trabajo Final de Máster (TFM)** para el *Máster Universitario en Ciencia de Datos* de la **Universitat Oberta de Catalunya (UOC)**.

**Autor:** José María Cases Gómez  
**Tutor/PRA:** Joaquín Torres-Sospedra  
**Área:** Pattern Recognition and Computer Vision in Applied Sciences  

---

## Descripción del Proyecto

El objetivo principal de esta investigación es desarrollar, evaluar y contrastar un sistema de posicionamiento en interiores robusto basado en *Wi-Fi Fingerprinting* utilizando el dataset público **UJIIndoorLoc**. 

A diferencia de los enfoques tradicionales basados en instancias, como el algoritmo *k-NN* utilizado aquí como *baseline*, este trabajo propone transformar los vectores unidimensionales de intensidad de señal (RSSI) en **matrices espaciales 2D**. Esta transformación habilita el uso de **Redes Neuronales Convolucionales (CNN)** para resolver de forma eficiente la macro-localización (edificio/planta) y la micro-localización (coordenadas métricas reales).

---

## Contenido del Repositorio

El repositorio está simplificado para facilitar la evaluación directa de la reproducibilidad del proyecto:

* **`Notebook_TFM.ipynb`**: Notebook de Jupyter que contiene todo el flujo de trabajo estructurado:
    1. Preprocesamiento y escalado de señales RSSI.
    2. Algoritmo de transformación de vectores a imágenes 2D.
    3. Implementación y entrenamiento del *baseline* k-NN.
    4. Diseño y entrenamiento del Clasificador Jerárquico.
    5. Desarrollo del modelo en Cascada (Especialistas por planta) y del modelo de Regresión Pura.
    6. Evaluación de métricas de precisión (MPE) y análisis de latencias.

* **`Notebook_TFM.html`**: Exportación estática del cuaderno en formato HTML para una visualización rápida directamente desde el navegador web.

---

## Tecnologías y Frameworks Utilizados

Los experimentos se han desarrollado en un entorno de **Python 3** utilizando las siguientes librerías principales:
* **TensorFlow / Keras**: Para el diseño, compilación y entrenamiento de las arquitecturas de aprendizaje profundo.
* **Scikit-learn**: Para la implementación del algoritmo clásico k-NN y métricas auxiliares.
* **Pandas & NumPy**: Para la manipulación y transformación matricial de las huellas Wi-Fi.
* **Matplotlib & Seaborn**: Para la extracción de gráficas y la Función de Distribución Acumulada (CDF).

---

## Nota sobre la Reproducibilidad

Para garantizar que todos los entrenamientos de las redes neuronales y las búsquedas de vecinos del k-NN arrojen exactamente los mismos resultados descritos en la memoria técnica, se ha establecido una **semilla estocástica global fija** al inicio del script tanto para el entorno de Python, NumPy y los inicializadores de pesos de TensorFlow.
