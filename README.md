Dataset

financial_fraud_detection_dataset.csv

El archivo CSV es demasiado grande para GitHub.  
[Descargar dataset desde Google Drive](https://drive.google.com/drive/folders/1-J_H_2kcWp5uvU_hNJ5UajPBMcq1KJjU?hl=es)

🛡️ Detección de Fraude Financiero con Machine Learning

Este proyecto desarrolla un sistema de **clasificación binaria** capaz de detectar transacciones fraudulentas en un dataset masivo (5 millones de registros), enfrentando el desafío crítico del **desbalance extremo de clases**.

---

📊 El Desafío del Negocio
En el sector financiero, el fraude representa pérdidas millonarias.  
Las transacciones fraudulentas son eventos raros (menos del 1% del total).  
El objetivo del modelo es **maximizar el Recall**, asegurando que casi ningún fraude pase desapercibido, manteniendo una eficiencia operativa alta.

---

🚀 Tecnologías Utilizadas
- **Lenguaje:** Python (Google Colab)  
- **Modelos:** Random Forest, XGBoost y **LightGBM** (Modelo que entrenó mejor los datos)  
- **Manejo de Desbalance:** Técnicas de Undersampling 
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
El modelo basa sus decisiones principalmente en variables de comportamiento transaccional (**Amount**), lo que permite una trazabilidad clara de por qué una transacción es marcada como sospechosa.

---

🛠️ Cómo utilizar el modelo

Descarga Directa

seguir los siguientes pasos:

    Hacer clic en el nombre del archivo (Detección_Fraude_Financiero.pkl).
    Buscar el botón que dice "Download" o "Download raw file".
    Guardarlo en su computadora.
---
Cómo usar el archivo en Python

import pickle

# Cargar el modelo o archivo
with open('Detección_Fraude_Financiero.pkl', 'rb') as archivo:
    modelo_cargado = pickle.load(archivo)

