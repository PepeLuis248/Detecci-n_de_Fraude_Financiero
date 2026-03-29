🛡️ Detección de Fraude Financiero con Machine Learning

![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)
![Scikit-Learn](https://img.shields.io/badge/Library-Scikit--Learn-orange.svg)
![LightGBM](https://img.shields.io/badge/Model-LightGBM-brightgreen.svg)

Este proyecto desarrolla un sistema de **clasificación binaria** capaz de detectar transacciones fraudulentas en un dataset masivo (5 millones de registros), enfrentando el desafío crítico del **desbalance extremo de clases**.

---

📊 El Desafío del Negocio
En el sector financiero, el fraude representa pérdidas millonarias.  
Las transacciones fraudulentas son eventos raros (menos del 1% del total).  
El objetivo del modelo es **maximizar el Recall**, asegurando que casi ningún fraude pase desapercibido, manteniendo una eficiencia operativa alta.

---

🚀 Tecnologías Utilizadas
- **Lenguaje:** Python (Google Colab)  
- **Modelos:** Random Forest, XGBoost y **LightGBM** (Ganador)  
- **Manejo de Desbalance:** Técnicas de Undersampling (**NearMiss**)  
- **Optimización:** GridSearchCV con validación cruzada estratificada  

---

📈 Resultados Comparativos

Tras evaluar múltiples modelos, el ganador fue **LightGBM** debido a su equilibrio entre velocidad y capacidad de detección:

| Métrica | Random Forest | XGBoost | LightGBM (Ganador) |
| :--- | :---: | :---: | :---: |
| **Recall (Sensibilidad)** | 0.94 | 1.00 | **1.00** |
| **Fraudes Perdidos (FN)** | 1,576 | 125 | **63** |
| **F1-Score** | 0.08 | 0.08 | 0.08 |

**Nota:** Se priorizó el Recall para minimizar el riesgo financiero.  
El modelo captura el **99.7%** de los intentos de fraude detectados en el set de prueba.

---

🔍 Análisis de Importancia de Variables
El modelo basa sus decisiones principalmente en variables de comportamiento transaccional (**V14, V17, Amount**), lo que permite una trazabilidad clara de por qué una transacción es marcada como sospechosa.

---

🛠️ Cómo utilizar el modelo
1. Clona el repositorio.  
2. Carga el archivo `lgbm_fraud_champion.pkl` usando `joblib`.  
3. Utiliza la función de predicción con umbral ajustable para equilibrar la precisión según las necesidades del negocio.  

```python
import joblib
modelo = joblib.load('lgbm_fraud_champion.pkl')

# Predicción con umbral personalizado
probabilidades = modelo.predict_proba(nuevos_datos)[:, 1]
veredicto = (probabilidades >= 0.7).astype(int)



