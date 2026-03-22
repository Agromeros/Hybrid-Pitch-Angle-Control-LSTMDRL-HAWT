# Control multiobjetivo del ángulo de paso en turbinas eólicas mediante un modelo híbrido de predicción y optimización

[![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)]
[![NumPy](https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white)](https://numpy.org/)
[![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)](https://pandas.pydata.org/)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-%23F7931E.svg?style=for-the-badge&logo=scikit-learn&logoColor=white)]
[![TensorFlow](https://img.shields.io/badge/tensor--flow-F7931E?style=for-the-badge&logo=tensorflow&logoColor=white)](https://www.tensorflow.org/)
[![Matplotlib](https://img.shields.io/badge/Matplotlib-%23ffffff.svg?style=for-the-badge&logo=Matplotlib&logoColor=black)]


## Resumen del trabajo
"Este trabajo de tesis aborda la creación de una metodología integrada que combina modelos de predicción del recurso eólico con técnicas de optimización de turbinas con el objetivo de maximizar la captura de energía, la estabilidad del rotor y el ajuste suave de las palas, lo que garantiza un equilibrio entre eficiencia y desgaste de sus principales componentes. El desafío central de esta investigación reside en demostrar cómo la integración predictiva con el control inteligente permite mejorar el desempeño dinámico y la salud mecánica de los aerogeneradores. Este enfoque permite la gestión automática del ángulo de las palas en función de la velocidad del viento pronosticada, lo que mitiga su impacto estocástico mientras extiende la vida útil de una turbina eólica.

En la primera etapa de este proyecto, se ha constuído un módulo de predicción de la velocidad del viento mediante redes neuronales de memoria de corto y largo plazo. En la segunda etapa, se han creado un agente de aprendizaje reforzado profundo, el cual ajusta la inclinación de las palas mediante una función de recompensa multiobjetivo que está diseñada para manejar la compensación entre la energía generada, la velocidad angular del rotor y el ajuste de las aspas. En la tercera etapa, se ha integrado el módulo de anticipación con el controlador del ángulo de paso. De esta manera, el sistema es capaz de actuar antes de que las variaciones del viento impacten la estructura.

Para demostrar y validar la propuesta, se ha implementado un modelo híbrido en dos entornos con características sumamente distintas: una turbina de alta capacidad en el norte de Chile y una turbina de menor capacidad en Suiza. En ambos casos la arquitectura del agente es altamente eficaz para optimizar la operación bajo condiciones climáticas distintas, lo que demuestra que la predicción del recurso eólico permite un control más estable sin limitar la generación de energía. 

De hecho, en el caso chileno, se logra captar más del noventa y cinco por ciento de la energía disponible y se redujeron los cambios bruscos en las piezas mecánicas en más de un cuarenta y dos por ciento. Mientras que en el caso suizo, se alcanzó más del setenta y dos por ciento de la eficiencia energética con una disminución de casi el sesenta por ciento en el impacto sobre la velocidad del rotor y de un veintitrés por ciento en las variaciones del ángulo de las aspas."

## Contacto
En caso de dudas, recomendaciones, discusiones contactar al autor por medio de github o por su correo electrónico (agromero@miuandes.cl)
