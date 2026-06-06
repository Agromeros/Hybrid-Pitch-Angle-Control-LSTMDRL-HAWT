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
La energía eólica es estocástica por naturaleza. El costo de esa imprevisibilidad es:
- Desgaste prematuro de las turbinas  
- Inestabilidad en la potencia generada  
- Reducción de la vida útil de los componentes mecánicos  

El **control del ángulo de paso (pitch)** es el mecanismo más crítico para contrarrestar este problema.  
Sin embargo, la mayoría de los controladores inteligentes optimizan un solo objetivo: la potencia.  

En la práctica, un operador necesita optimizar simultáneamente:  
- **Máxima energía**  
- **Estabilidad del rotor**  
- **Reducción de cambios bruscos en el ángulo de las palas**  

---

## ⚙️ Arquitectura del modelo híbrido

| Arquitectura Conceptual | Arquitectura Modular |
|-------------------------|----------------------|
| ![Arquitectura Conceptual](ruta/imagen_conceptual.png) | ![Arquitectura Modular](ruta/imagen_modular.png) |

**Módulo 1 — Predicción (LSTM)**  
Anticipa la velocidad del viento antes de que impacte las palas.  

**Módulo 2 — Entorno (kNN)**  
Modela la dinámica de la turbina con datos operacionales.  

**Módulo 3 — Control (DDPG)**  
Agente de Deep Reinforcement Learning que ajusta el ángulo de paso optimizando:  
- Potencia generada  
- Estabilidad del rotor  
- Reducción de fatiga mecánica  

---

## 📊 Resultados

| Chile (Taltal, Vestas V-112, 3 MW) | Suiza (Taggenberg, Aventa AV-7, 6 kW) |
|------------------------------------|---------------------------------------|
| ![Resultados Chile](ruta/imagen_chile.png) | ![Resultados Suiza](ruta/imagen_suiza.png) |

**Chile:** eficiencia integrada = **806,635**  
**Suiza:** eficiencia integrada = **0,356**  

> En ambos casos, el modelo híbrido supera la eficiencia obtenida con viento real y datos reales, demostrando un mejor balance entre rendimiento energético y estabilidad de control.

---

## 👤 Autor

**Alonso Romero Sánchez**  
Egresado Ingeniería Civil Industrial | Data Science · ML · Deep RL  

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Alonso_Romero-blue)](https://www.linkedin.com/in/alonsoromerosanchez)  
[![Email](https://img.shields.io/badge/Email-agromero%40miuandes.cl-red)](mailto:agromero@miuandes.cl)  

*Si este proyecto te resulta útil o tienes preguntas, escríbeme — me interesa conectar.*
