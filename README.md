# Control multiobjetivo del ángulo de paso en turbinas eólicas mediante un modelo híbrido de predicción y optimización

![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
![Google Colab](https://img.shields.io/badge/Google%20Colab-%23F9A825.svg?style=for-the-badge&logo=googlecolab&logoColor=white)
![Visual Studio Code](https://img.shields.io/badge/Visual%20Studio%20Code-0078d7.svg?style=for-the-badge&logo=visual-studio-code&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-%23F7931E.svg?style=for-the-badge&logo=scikit-learn&logoColor=white)
![TensorFlow](https://img.shields.io/badge/tensor--flow-F7931E?style=for-the-badge&logo=tensorflow&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-%23ffffff.svg?style=for-the-badge&logo=Matplotlib&logoColor=black)


## Problema 
La energía eólica es estocástica por naturaleza, el costo de esa imprevisibilidad es el desgaste de la turbinas antes de tiempo, la inestabilidad de la potencia y la disminución de la vida útil en los componentes mecánicos sometidos a cargas.

El control del ángulo de paso (pitch) es el mecanismo más crítico para contrarrestar este problema. Sin embargo, la mayoría de los controladores inteligentes optimizan un solo objetivo: la potencia. En la práctica, un operador necesita, simultáneamente, optimizar 3 factores:
**máxima energía, minimizar la variabilidad del rotor y minimizar los cambios bruzcos en el ángulo de las palas.** 

Los objetivos planteados se contradicen entre sí, es por este motivo que el proyecto propone una solución: un sistema híbrido que combina **predicción de viento (LSTM)** con un **agente de control inteligente (DDPG)** guiado por una **función de recompensa multiobjetivo**.

## Arquitectura del modelo híbrido

El sistema se compone de dos módulos interconectados:
```
Datos meteorológicos históricos → LSTM → Velocidad predicha
                                                  ↓
                     Datos operacionales → [Entorno k-NN] → Estado
                                                               ↓
                              Recompensa multiobjetivo → Agente DDPG → Δ Ángulo de paso (Desición)                      
                           (Potencia + Estabilidad + Fatiga)    
```

**Módulo 1 — Predicción (LSTM)**
Consiste en una red neuronal recurrente tipo LSTM entrenada con variables meteorológicas para anticipar la velocidad del viento antes de que impacte las palas.

**Módulo 2 — Control (DDPG)**
Consiste en un agente de Deep Reinforcement Learning, DDPG, que ajusta el ángulo de paso en función del viento predicho, optimizando simultáneamente:
- Maximización de potencia generada
- Estabilidad de la velocidad angular del rotor → Minimizar los cambios bruscos
- Reducción de fatiga mecánica del actuador → Minimizar los cambios bruscos

## 📊 Resultados

Validado en dos entornos con características climáticas y técnicas opuestas:

| Métrica | Taltal, Chile | Taggenberg, Suiza |
|---|---|---|
| Turbina | Vestas V-112 (3 MW) | Aventa AV-7 (6 kW) |
| Potencia Agente LSTM-DDPG vs. Agente real-DDPG | 95.2% | 72.2% |
| Reducción cambios bruscos de pitch | −42.5% | −23.1% |
| Impacto en velocidad del rotor | +0.02% | −59.5% |

> El modelo híbrido captura casi toda la energía de un controlador con información perfecta y reduce el desgaste mecánico.

## Autor

**Alonso Romero Sánchez**
Egresado Ingeniería Civil Industrial | Data Science · ML · Deep RL

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Alonso_Romero-blue)](https://www.linkedin.com/in/alonsoromerosanchez)
[![Email](https://img.shields.io/badge/Email-agromero%40miuandes.cl-red)](mailto:agromero@miuandes.cl)

*Si este proyecto te resulta útil o tienes preguntas, escríbeme — me interesa conectar.*
