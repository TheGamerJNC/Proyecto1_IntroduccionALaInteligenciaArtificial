 # *Adicción a los Videojuegos en personas con TEA:* Factores desencadenantes, impacto funcional y repercusiones a largo plazo

***Definición del problema*** \
\
El uso de videojuegos ha aumentado significativamente en los últimos años, convirtiéndose en una de las principales formas de entretenimiento digital. Sin embargo, un uso excesivo puede estar asociado a efectos negativos sobre la salud mental, incluyendo mayores niveles de ansiedad, estrés, depresión y dificultades en el bienestar general. Comprender qué factores del comportamiento de juego se relacionan con estos efectos resulta relevante para identificar perfiles de riesgo y promover hábitos de uso más saludables.

***Dataset: Descripción y Fuente*** \
\
*Gaming and Mental Health Dataset (https://www.kaggle.com/datasets/shaistashahid/gaming-and-mental-health)* \
Este dataset se centra en la relación entre el uso de videojuegos y la salud mental. Contiene variables relacionadas con bienestar psicológico, niveles de estrés, ansiedad, estado de ánimo y hábitos de juego. Permite analizar cómo el gaming se asocia con diferentes indicadores de salud mental, aportando una dimensión clínica y psicológica al análisis del comportamiento adictivo.

***Modelos seleccionados*** \
\
*Random Forest* \
Modelo principal de clasificación. Permite manejar relaciones no lineales entre variables, trabajar con datos mixtos y obtener la importancia de cada variable en la predicción.

*Regresión Logística* \
Es un modelo de clasificación que estima la probabilidad  de que una observación pertenezca a una determinada categoría. Es ampliamente utilizada para problemas de clasificación binaria. 

*K-Nearest Neighbors (KNN)* \
Es un algoritmo de clasifiación que asgina una categoría a una observación según las clases de sus vecinos cercanos en el conunto de datos. Su funcionamiento se basa en las simulitudes entre las caracteristicas de los individuos. 

***Justificación de los Modelos*** \
\
El problema planteado busca analizar la relación entre el uso problemático de videojuegos y el riesgio de daño hacia la salud mental. 

*Random Forest* \
Pertinencia: Es pertinente para este proyecto porque la relación entre los hábitos de juego y la salud mental puede depender de múltiples variables que interactúan entre sí, como las horas de juego, la edad, el género y la experiencia en videojuegos. Este modelo permite capturar relaciones complejas sin necesidad de asumir una estructura lineal de los datos.

 Ventajas: 
  - Maneja variables numéricas y categóricass.
  - Buen manejo de variables mixtas.
  - Permite medir importancia de variables.

 Limitaciones: 
  - Puede ser computacionalmente más costoso de trabajar.

Justificación: Se selecciona como modelo principal debido a su capacidad para trabajar con variables numéricas y categóricas simultáneamente, manejar grandes volúmenes de información y reducir el riesgo de sobreajuste mediante la combinación de múltiples árboles de decisión.

*Regresión Logística* \
Pertinencia: Es adecuada para este proyecto cuando el objetivo es clasificar a los jugadores en categorías de riesgo, por ejemplo, riesgo alto o bajo de afectación de la salud mental. Permite modelar la probabilidad de pertenecer a una determinada clase en función de las características observadas.

 Ventajas: 
  - Permite comprender fácilmente cómo cada variable influye en la predicción.
  - Esta diseñada para predecir la probabilidad de que una variable pertanezca a una clase. 

 Limitaciones: 
  - Puede perder precisión si el fenónmeno es complejo.

Justificación: Se utiliza como modelo de referencia debido a su simplicidad e interpretabilidad. Sus resultados permiten comprender cómo cada variable influye en la probabilidad de presentar problemas de salud mental asociados a los hábitos de juego.

*K-Nearest Neighbors (KNN)* \
Pertinencia: Resulta pertinente porque clasifica a los individuos según su similitud con otros jugadores presentes en el conjunto de datos. Esto permite identificar perfiles con características de juego y salud mental similares, facilitando la detección de grupos de riesgo.

  Ventajas:
  - Simple y facil de interpretar conceptualmente.
  - Útil para detectar agrupaciones naturales.

  Limitaciones:
  - Alto costo computacional en grandes datasets.
  - Rendimiento depende fuertemente de la elección de K.

Justificación: El modelo permite analizar cómo jugadores con hábitos similares pueden presentar niveles parecidos de afectación en su salud mental. Además, proporciona una perspectiva complementaria a los modelos basados en reglas o probabilidades, enriqueciendo el análisis comparativo del proyecto.

***Métricas Seleccionadas (y su Justificación)*** \
\
*Precision*
- Lo que mide: El porcentaje de personas identificadas con adicción que realmente la padecen.
- El por que es útil: Un falso positivo (no etiquetar incorrectamente a alguien como en riesgo). Importante porque evita diagnósticos erróneos. 

*Recall*
- Lo que mide: El porcentaje de personas con adicción real que el modelo logra detectar.
- El por que es útil: Permite identificar personas que realmente pueden tener afectación en salud mental. 

*F1-Score*
- Lo que mide: La media armónica entre "Precision" y "Recall".
- El por que es útil: Los datos sobre adicción en poblaciones específicas suelen estar muy desbalanceados (la mayoría de la muestra no cumplirá con los criterios clínicos de adicción). El F1-Score es la mejor métrica general para evaluar el rendimiento del modelo sin dejarse engañar por una alta precisión a costa de un recall bajo, o viceversa.

*AUC-ROC (Área debajo de la curva ROC)*
- Lo que mide: La capacidad del modelo para distinguir entre ambas clases a través de diferentes umbrales de decisión.
- El por que es útil: Permite evaluar que tan bien el modelo separa jugadores con y sin riesgo. Es muy útil cuando las clases no están equilibradas. 
