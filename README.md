 # Análisis del impacto del uso de videojuegos en el bienestar psicológico.

***Pregunta del problema*** 

¿Es posible predecir el impacto negativo en la salud mental asociado al uso excesivo de videojuegos a partir de variables de hábitos de juego?

***Definición del problema*** \
\
El uso de videojuegos ha aumentado significativamente en los últimos años, convirtiéndose en una de las principales formas de entretenimiento digital. Sin embargo, un uso excesivo puede estar asociado a efectos negativos sobre la salud mental, incluyendo mayores niveles de ansiedad, estrés, depresión y dificultades en el bienestar general. Comprender qué factores del comportamiento de juego se relacionan con estos efectos resulta relevante para identificar perfiles de riesgo y promover hábitos de uso más saludables.

***Dataset: Descripción y Fuente*** \
\
*Gaming and Mental Health Dataset (https://www.kaggle.com/datasets/shaistashahid/gaming-and-mental-health)* \
Este dataset se centra en la relación entre el uso de videojuegos y la salud mental. Contiene un total de 26 dimensiones o columnas (sin contar la que contiene la variable a predecir), con features relacionadas con bienestar psicológico, niveles de estrés, ansiedad, estado de ánimo y hábitos de juego (en otras palabras, contiene diferentes características relacionadas con la adicción a los videojuegos). En este caso particular, la variable a predecir es **'gaming\_addiction\_risk\_level'**, la cual nos entrega el nivel de riesgo o probabilidad de que el usuario analizado padezca esta adicción. Entre las features usadas en el dataset podemos nombrar *'daily\_gaming\_hours'* (que nos entrega la cantidad de horas de juego diarias), *'sleep\_hours'* (que nos entrega las horas de sueño), *'academic\_work\_performance'* (que nos da a conocer el grado de rendimiento académico o laboral), entre muchas otras más que nos entregan información útil para la etapa de predicción. En pocas palabras, el dataset seleccionado nos permite analizar cómo el gaming se asocia con diferentes indicadores de salud mental, aportando una dimensión clínica y psicológica al análisis del comportamiento adictivo.

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

***Resultados*** \
\
*Comparación de Modelos (Métricas)* \
**Tabla**
<table>
	<tr>
		<th>Modelo</th>
		<th>Clase</th>
		<th>Accuracy</th>
		<th>Precision</th>
		<th>Recall</th>
		<th>F1-Score</th>
	</tr>
	<tr>
		<td rowspan="4">Regresión Logística</td>
		<td>0</td>
		<td rowspan="4">0.95</td>
		<td>0.87</td>
		<td>0.87</td>
		<td>0.87</td>
	</tr>
	<tr>
		<td>1</td>
		<td>1.00</td>
		<td>1.00</td>
		<td>1.00</td>
	</tr>
	<tr>
		<td>2</td>
		<td>0.88</td>
		<td>1.00</td>
		<td>0.93</td>
	</tr>
	<tr>
		<td>3</td>
		<td>1.00</td>
		<td>0.86</td>
		<td>0.92</td>
	</tr>
	<tr>
		<td rowspan="4">Random Forest</td>
		<td>0</td>
		<td rowspan="4">0.94</td>
		<td>0.86</td>
		<td>0.81</td>
		<td>0.83</td>
	</tr>
	<tr>
		<td>1</td>
		<td>1.00</td>
		<td>0.99</td>
		<td>1.00</td>
	</tr>
	<tr>
		<td>2</td>
		<td>0.84</td>
		<td>0.94</td>
		<td>0.89</td>
	</tr>
	<tr>
		<td>3</td>
		<td>0.96</td>
		<td>0.92</td>
		<td>0.94</td>
	</tr>
	<tr>
		<td rowspan="4">K-Nearest Neighbors (KNN)</td>
		<td>0</td>
		<td rowspan="4">0.82</td>
		<td>0.63</td>
		<td>0.71</td>
		<td>0.67</td>
	</tr>
	<tr>
		<td>1</td>
		<td>0.90</td>
		<td>0.99</td>
		<td>0.94</td>
	</tr>
	<tr>
		<td>2</td>
		<td>0.67</td>
		<td>0.56</td>
		<td>0.61</td>
	</tr>
	<tr>
		<td>3</td>
		<td>0.94</td>
		<td>0.68</td>
		<td>0.79</td>
	</tr>
</table>

**Observaciones**

<ol start=1>
<li>El alto rendimiento de la Regresión Logística (el alto valor de "Accuracy") sugiere que existe una relación fuertemente lineal y directa entre las características evaluadas (como las horas de juego o los niveles de ansiedad) y la clasificación del riesgo. Esto nos demuestra que las clases de adicción en este dataset no requieren de transformaciones complejas para ser identificadas con alta precisión.</li>
<li>Aunque "Random Forest" es un modelo robusto frente al sobreajuste (y también subajuste), su rendimiento comparativo nos indica que la complejidad adicional no era estrictamente necesaria para la estructura de este dataset. Sin embargo su principal aporte radica en la ayuda que nos aportó al permitirnos extraer la "importancia de las variables", confirmando numéricamente cuáles de los factores de los hábitos de juego pesan más al momento de tratar de predecir el riesgo.</li>
<li>Como se puede notar, el modelo "K-Nearest Neighbors" presentó un rendimiento mucho menor que los dos modelos anteriores, lo cual debido al concepto de la "Maldición de la Dimensionalidad" visto en clases es de esperarse. Al ser un algoritmo basado en la distancia (euclidiana, por ejemplo) entre puntos de los datos, la presencia de múltiples variables en el dataset en cuestión puede atenuar (o disminuir) la proximidad real entre los usuarios con perfiles psicológicos similares, haciéndolo más sensible al ruido en comparación con los otros modelos usados previamente.</li>
</ol>

*Importancia de las Características* \
En cuanto a la importancia de las características del modelo de "Random Forest", podemos hablar de los tres factores que generan un mayor impacto en el riesgo de adicción.

<ol start=1>
<li> <b>daily_gaming_hours</b>: Representa la cantidad total de horas jugadas por día del jugador/a. Es de esperarse que esta sea la característica con mayor impacto en el riesgo de adicción, ya que entre más tiempo juega una persona, aumenta cada vez más el riesgo de padecer esta adicción.</li>
<li> <b>loss_of_other_interests</b>: Representa de forma binaria (True = SI, False = NO) la pérdida de otros intereses de los jugadores/as. Que éste sea la segunda característica con más peso, nos dice que la mayoría de los usuarios que pierden interés en todo lo que no sea videojuegos representa un claro síntoma o factor de riesgo de una posible adicción.</li>
<li> <b>withdrawal_symptoms</b>: Identifica a los/as usuarios que padecen síntomas de abstinencia luego de dejar de jugar por lapsos prolongados. Y, el simple hecho de que esté ubicada como la tercera característica más relevante, nos entrega la idea de que, a pesar que solo el 29% de los jugadores/as de los datos posee síndrome de abstinencia, éste dato es uno de los más importantes a la hora de diagnosticar esta adicción.</li>
</ol>

*Análisis de las Matrices de Confusión* \
En cuanto a las matrices de confusión de cada método, podemos destacar dos aspectos particulares a notar (sin contar la matriz de confusión de _K-Nearest Neighbors_, debido a que es la que posee la mayor tasa de errores de clasificación).

<ol start=1>
<li>Si vemos la matriz de confusión de la _Regresión Logística_, podemos notar que es la que posee la menor cantidad de clasificaciones erróneas (era de esperarse debido a ser también la que posee el mayor valor de "Accuracy" con un valor de 0.95) con un total de 14. Debido a esto, este es el modelo que nos entrega los resultados más confiables de los tres.</li>
<li>Hablando ahora del _Random Forest_, vemos que su matriz de confusión es el punto medio de los tres modelos. Este nos entrega una seguridad elevada de sus cálculos, con un total de 18 clasificaciones erróneas. Y, al tener un valor de "Accuracy" menor que la _Regresión Logística_, se infiere que (tal como esperamos) su rendimiento y capacidad de predicción se ve opacada por el anterior.</li>
</ol>

***Conclusión*** \
\
El presente proyecto tuvo como objetivo analizar si es posible predecir el impacto negatvo en la salud mental asociado al uso de videojuegos a partir de variables relacionadas con los hábitos de juego, utilizando modelos como Regresión Logística, Random Forest y K-Nearest Neighbors. A partir de los resultados obtenidos, se puede concluir que la hipótesis del estudio se cumple, ya que los modelos implementados fueron capaces de predecir con un alto nivel de desempeño el riesgo de afectación en la salud mental de los jugadores. En particular, tanto el modelo Regresion Logística como Random Forest mostraron valores elevados de Precisión, Recall y F1-Score, además de una buena capacidad discriminativa según las matrices de confusión. Por otro lado, el modelo K-Nearest Neighbors presentó un desempeño inferior en comparación a los demás modelos, lo que sugiere que la problemática no se explica únicamente mediante similitud entre casos, sino que requiere modelos capaces de capturar relaciones más complejas entre las variables. 

Por otro lado, los resultados permiten identificar variables como las horas diarias de juego, la pérdida de interés en otras actividades, el aislamieno social y la calidad de sueño, los cuales son factores determinantes para la predicción del riesgo, lo que confirma que el impacto del uso de videojuegos no depende de un único factor, sino de la combinación de múltiples variables conductuales y psicológicas.

En conclusión, el estudio demuestra que sí es posible predecir el impacto negativo en la salud mental asociado al uso de videojuegos mediante modelos de machine learning, validando la pregunta a la investigación de dicho proyecto. Se puede agregar que los resultados obtenidos evidencian que el uso excesivo de videojuegos, junto con ciertos patrones de comportamiento, se asocia significativamente a una mayor probabilidad de afectación en la salud mental de los jugadores.
