# Data Mining con IA: Factores de Éxito en E-Commerce 🚀

## 1. Objetivo y Pregunta Central
¿Qué características del producto (Precio, Categoría, Descuento, Calificación de usuarios) determinan que se convierta en un éxito de ventas (60 o más unidades vendidas)?

## 2. Fuente de los Datos y Limpieza
* **Tamaño:** 300 registros (productos).
* **Proceso de Limpieza con IA:**
  * Homogeneización de texto en la variable `Categoria` (corrección de mayúsculas/minúsculas).
  * Imputación de precios erróneos (valores negativos de -99.0) utilizando la mediana por categoría.
  * Rellenado de valores nulos (`NaN`) en `Calificacion` con el promedio general.
  * Creación de la variable objetivo binaria `Exito_Ventas`.

## 3. Técnica de Minería de Datos Aplicada
* **Algoritmo:** Árbol de Decisión (Clasificación binaria).
* **División de datos:** 80% entrenamiento, 20% prueba.
* **Resultado obtenido:** Precisión general (Accuracy) de 51.67%.

## 4. Conclusiones y Recomendaciones
* **Insight principal:** Con las variables actuales, el modelo tiene un rendimiento cercano al azar. Esto nos indica que el éxito de ventas en e-commerce es un fenómeno complejo que no depende únicamente del precio o la categoría.
* **Limitaciones:** Dataset acotado a 300 registros sintéticos.
* **Recomendaciones futuras:** Incorporar variables cualitativas como "comentarios de clientes", "gasto en publicidad" o "mes de venta" (estacionalidad) para mejorar la precisión del modelo.

## 5. Video Explicativo del Proyecto
* [Haz clic aquí para ver el video explicativo](Pega_aquí_el_enlace_de_tu_video)
