1. Preparación del entorno
Se monta Google Drive para acceder al dataset almacenado.
Se descomprime un archivo .zip que contiene imágenes etiquetadas como somnoliento (drowsy) o no somnoliento (non_drowsy).

2. Preprocesamiento de datos
Conversión a escala de grises:
Las imágenes originales se convierten a escala de grises para reducir complejidad y enfocar el análisis en la intensidad de los píxeles.
Almacenamiento estructurado:
Las imágenes procesadas se guardan en nuevas carpetas (grayscale_drowsy y grayscale_non_drowsy) y se almacenan sus representaciones como vectores para ser usadas en el entrenamiento del modelo.
Exploración inicial:
Se visualizan imágenes originales y en escala de grises para verificar el preprocesamiento.

3. Análisis de datos
Se calcula la cantidad de imágenes por clase y su tamaño en bytes, tanto en el estado original como en escala de grises.
Se genera un DataFrame para organizar las características (vectores de píxeles) y las etiquetas correspondientes (somnoliento: 1, no somnoliento: 0).

4. Entrenamiento del modelo
Se divide el dataset en conjuntos de entrenamiento (80%) y prueba (20%) usando train_test_split de scikit-learn, asegurando un balance entre clases.
Se entrena un clasificador SVM (Support Vector Machine) con un kernel lineal para identificar patrones entre las características y las etiquetas.
Se evalúa el modelo calculando la precisión tanto en el conjunto de entrenamiento como en el conjunto de prueba.

5. Pruebas con datos adicionales
Se prueban imágenes adicionales fuera del conjunto inicial para evaluar el desempeño del modelo en escenarios no vistos.
Las imágenes de prueba se procesan de manera similar (escala de grises y conversión a vectores) antes de realizar predicciones.

6. Visualización de resultados
Se presentan gráficamente las imágenes procesadas y se muestran métricas de desempeño del modelo.

Resultados esperados:
Una métrica de precisión razonable que indique qué tan bien el modelo puede diferenciar entre estados de somnolencia y alerta basándose en las imágenes.
Un sistema que permita futuras mejoras, como el uso de redes neuronales para un análisis más avanzado.
