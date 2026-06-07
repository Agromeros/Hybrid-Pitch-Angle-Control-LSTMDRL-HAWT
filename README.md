# Control multiobjetivo del ángulo de paso en turbinas eólicas mediante un modelo híbrido de predicción y optimización

![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
![Google Colab](https://img.shields.io/badge/Google%20Colab-%23F9A825.svg?style=for-the-badge&logo=googlecolab&logoColor=white)
![Visual Studio Code](https://img.shields.io/badge/Visual%20Studio%20Code-0078d7.svg?style=for-the-badge&logo=visual-studio-code&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-%23F7931E.svg?style=for-the-badge&logo=scikit-learn&logoColor=white)
![TensorFlow](https://img.shields.io/badge/tensor--flow-F7931E?style=for-the-badge&logo=tensorflow&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-%23ffffff.svg?style=for-the-badge&logo=Matplotlib&logoColor=black)

---

## 📌 Problema
La **velocidad del viento es estocástica**, no se puede saber con certeza su disponibilidad. 
Además, los **controladores tradicionales reaccionan al viento observado y suelen asumir comportamientos lineales. Esto limita su capacidad para operar bajo incertidumbre y equilibrar simultáneamente captura energética, estabilidad del rotor y desgaste mecánico.

El **control del ángulo de paso (pitch)** el componente con mayor impacto en la eficiencia y seguridad de un aerogenerador. 
Sin embargo, la mayoría de los controladores inteligentes optimizan un solo objetivo: la potencia.  

En la práctica, un operador necesita optimizar simultáneamente:  
- **Máxima energía**  
- **Estabilidad del rotor**  
- **Reducción de cambios bruscos en el ángulo de las palas**  

---

## ⚙️ Arquitectura del modelo híbrido

| Flujo de datos | Deep Reinforcement Learning |
|-------------------------|----------------------|
| ![Flujo de datos](Imagenes/FlujoDatos.png) | ![Deep Reinforcemen Learning](Imagenes/DRL.png) |

**Módulo 1 — Predicción (LSTM)**  
Pronostica la velocidad del viento mediante una red LSTM alimentada de datos meteorológicos

**Módulo 2 — Entorno (kNN)**  
Modela la dinámica de los datos operacionales relacionandolos mediante un K-Nearest neightboors. Se utiliza debido a la confidencialidad de los datos de la trurbina con el fin de obtener una transición de estados.

**Módulo 3 — Control (DDPG)**  
Agente DDPG, en el paradigna de Deep Reinforcement Learning, que ajusta el ángulo de paso optimizando:  
- Potencia generada  
- Estabilidad del rotor  
- Reducción de fatiga mecánica  

**Recompensa del Agente**

![Recompensa Multiobjetivo](Imagenes/Reward.png)

- R_t: Recompensa
- w₁, w₂, w₃: Pesos relativos
- Pₜ, Pₘₐₓ: Potencia
- ωₜ, ωᵣₑ𝒻: Velocidad angular del rotor
- βₜ, Δβₜ, βₘₐₓ: Ángulo de paso

---

## 📊 Resultados

Chile (Taltal, Vestas V-112, 3 MW)
![Resultados Chile](Imagenes/Resultados_Chile.png)

Suiza (Taggenberg, Aventa AV-7, 6 kW)
![Resultados Suiza](Imagenes/Resultados_Suiza.png)

> En ambos casos, el modelo híbrido supera la eficiencia obtenida con viento real y datos reales, demostrando un mejor balance entre rendimiento energético y estabilidad de control.

---

## 👤 Autor

**Alonso Romero Sánchez**  
Ingeniero Civil Industrial | Data Science · ML · Deep RL  

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Alonso_Romero-blue)](https://www.linkedin.com/in/alonsoromerosanchez)  
[![Email](https://img.shields.io/badge/Email-agromero%40miuandes.cl-red)](mailto:agromero@miuandes.cl)  

*Si este proyecto te resulta útil o tienes preguntas, escríbeme — me interesa conectar.*
