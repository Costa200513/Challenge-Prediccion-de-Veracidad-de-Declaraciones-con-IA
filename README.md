# Predicción de Veracidad de Declaraciones con IA

## Introducción

Este proyecto implementa un modelo de **Inteligencia Artificial (IA)** diseñado para predecir la veracidad de declaraciones públicas, clasificándolas como **verdaderas (True)** o **falsas (False)**.  
El enfoque se basa en un modelo de **Machine Learning supervisado**, específicamente el algoritmo **K-Nearest Neighbors (KNN)**, entrenado a partir de datos históricos de declaraciones y características contextuales como el tema, la afiliación política y el historial del orador.

---

## Preprocesamiento de Datos

La etapa de preprocesamiento tuvo como propósito preparar el conjunto de datos para optimizar el rendimiento del modelo.  
Se trabajó sobre el archivo `df_train.csv`, que contenía las variables categóricas y numéricas necesarias para el entrenamiento.

El proceso incluyó:

- Conversión de la variable objetivo (**Etiqueta**) a valores numéricos:  
  - `True` → **1**  
  - `False` → **0**
- Mapeo de variables categóricas como **Afiliación Política**, **Estado**, **Orador** y **Tema**, asignando valores numéricos a cada categoría.
- Reemplazo de valores nulos por **0** para evitar errores durante el entrenamiento.

<img width="844" height="668" alt="image" src="https://github.com/user-attachments/assets/de590e2e-3fa9-4591-825e-f30a13cc60a1" />
<img width="785" height="140" alt="image" src="https://github.com/user-attachments/assets/68330a9f-0705-48bb-8cf4-639f34e46aa7" />

---

## Desarrollo del Modelo

Una vez preparado el conjunto de datos, se seleccionaron las columnas más relevantes y se entrenó un modelo de **clasificación supervisada** utilizando el algoritmo **K-Nearest Neighbors (KNN)** con el parámetro `n_neighbors = 5`.

El dataset se dividió en dos subconjuntos:

- **80%** para el **entrenamiento**
- **20%** para la **prueba**

Este enfoque permitió evaluar la capacidad del modelo para generalizar correctamente en datos no vistos.

## Variables Independientes Utilizadas

Las variables seleccionadas para el entrenamiento del modelo fueron:

- **Cantidad Verdadera**: número de declaraciones previas del orador clasificadas como verdaderas.  
- **Cantidad Falsa**: número de declaraciones previas clasificadas como falsas.  
- **Afiliación Política**: partido o tendencia política del orador.  
- **Tema**: categoría o temática de la declaración (por ejemplo, economía, salud o educación).

La **variable dependiente u objetivo** fue **Etiqueta**, la cual indica si la declaración es **verdadera (1)** o **falsa (0)**.

---

## Evaluación y Predicción

El rendimiento del modelo se evaluó utilizando el conjunto de prueba (**20% de los datos**).  
La **exactitud (accuracy)** se calculó mediante el método `.score()`, lo que permitió medir la proporción de predicciones correctas sobre el total de casos analizados.

<img width="459" height="111" alt="image" src="https://github.com/user-attachments/assets/35ebebfc-f34e-4580-be9b-1e2b56fae1dc" />

El modelo alcanzó aproximadamente un 60% de exactitud, lo que demuestra una capacidad moderada para distinguir entre declaraciones verdaderas y falsas.
Este resultado refleja que, si bien el modelo logra identificar ciertos patrones en los datos, aún existe margen de mejora mediante el ajuste de parámetros o el uso de algoritmos más complejos.


