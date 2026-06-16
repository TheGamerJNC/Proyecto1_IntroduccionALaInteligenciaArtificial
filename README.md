b# *Adicción a los Videojuegos en personas con TEA:* Factores desencadenantes, impacto funcional y repercusiones a largo plazo

***Definición del problema*** \
\
El uso de videojuegos se ha incrementado significativamente en los últimos años, especialmente en población joven, generando en algunos casos patrones de uso problemático o adictivo. Diversos estudios sugieren que ciertos grupos neurodivergentes, como las personas dentro del Trastorno del Espectro Autista (TEA), podrían presentar una relación distinta con este tipo de estímulos digitales, debido a características como la preferencia por rutinas, intereses restringidos y alta focalización en actividades específicas.

Sin embargo, aún no existe claridad sobre si estas características se asocian a una mayor severidad del uso problemático de videojuegos o si simplemente reflejan formas distintas de interacción con el entorno digital. Esto genera una brecha en la comprensión del fenómeno, especialmente en la identificación de factores conductuales y neurobiológicos que podrían influir en el desarrollo de patrones de uso excesivo.

***Datasets: Descripción y Fuente*** \
\
*Gaming Addiction Dataset (https://www.kaggle.com/datasets/ajitashwath/gaming-addiction-dataset)* \
Este dataset contiene información relacionada con hábitos de uso de videojuegos y posibles indicadores de adicción. Incluye variables como horas de juego, control del comportamiento, impacto emocional del gaming y señales de uso problemático. Su objetivo principal es permitir la identificación de patrones conductuales asociados al uso excesivo de videojuegos.

*Survey on Video Game Addiction and Academic Performance (https://www.kaggle.com/datasets/laujinxi/survey-on-video-game-addiction-and-academic)* \
Dataset basado en encuestas que recopila información sobre hábitos de videojuegos, características personales y variables de contexto del usuario. Incluye indicadores conductuales y de estilo de vida que permiten analizar el uso de videojuegos desde una perspectiva social y conductual, aportando información relevante sobre patrones de adicción.

*Gaming and Mental Health Dataset (https://www.kaggle.com/datasets/shaistashahid/gaming-and-mental-health)* \
Este dataset se centra en la relación entre el uso de videojuegos y la salud mental. Contiene variables relacionadas con bienestar psicológico, niveles de estrés, ansiedad, estado de ánimo y hábitos de juego. Permite analizar cómo el gaming se asocia con diferentes indicadores de salud mental, aportando una dimensión clínica y psicológica al análisis del comportamiento adictivo.

*Autism Spectrum Disorder Clasification (https://www.kaggle.com/competitions/abide)* \
El objetivo del presente estudio fue aplicar algoritmos de aprendizaje profundo para identificar a pacientes con trastorno del espectro autista (TEA) a partir de un gran conjunto de datos de imágenes cerebrales, basándose únicamente en los patrones de activación cerebral de los pacientes. Investigamos datos de neuroimagen de pacientes con TEA de una base de datos mundial multisitio conocida como ABIDE (Intercambio de Datos de Imagen Cerebral Autista). El TEA es un trastorno cerebral caracterizado por déficits sociales y conductas repetitivas.

***Modelos seleccionados*** \
\
*Random Forest* \
Modelo principal de clasificación. Permite manejar relaciones no lineales entre variables, trabajar con datos mixtos y obtener la importancia de cada variable en la predicción.

*K-Nearest Neighbors (KNN)* \
Modelo basado en similitud entre observaciones. Permite identificar patrones de usuarios con comportamientos similares en términos de uso de videojuegos y rasgos asociados al TEA.

***Justifiación de los Modelos*** \
\
El problema planteado busca analizar la relación entre el uso problemático de videojuegos y los rasgos asociados al Trastorno del Espectro Autista (TEA), integrando además variables conductuales y de salud mental. Dado que el objetivo principal es clasificar perfiles de riesgo de uso problemático de videojuegos y comprender qué variables influyen en este comportamiento.

*Random Forest* \
Pertinencia: Es el modelo mas adecuado para el problema, ya que permite manejar múltiples variables muy disntintas entre si, provenientes de los disntintos datasets (Conductuales, psicológicos y neurobiológicos).

 Ventajas: 
  - Captura relaciones no lineales complejas.
  - Buen manejo de variables mixtas.
  - Permite medir importancia de variables.

 Limitaciones: 
  - Puede ser computacionalmente mas costoso de trabajar.

Justificación: Es el modelo mas adecuadopara detectar patrones complejos entre uso de videojuegos, salud mental y ragos de TEA, que no necesariamente siguen relaciones lineales.

*K-Nearest Neighbors (KNN)* \
\
Pertinencia: Permite identificar usuarios con comportamiento similares en términos de gaming y características psicológicas/neurobiológicas.

  Ventajas:
  - Simple y facil de interpretar conceptualmente.
  - Útil para detectar agrupaciones naturales.

  Limitaciones:
  - Alto costo computacional en grandes datasets.
  - Rendimiento depende fuertemente de la elección de K.

Justificación: Es útil para explorar similitudes entre perfiles de usuarios, especialmente entre individuos con rasgos TEA y los que no presentan TEA.
