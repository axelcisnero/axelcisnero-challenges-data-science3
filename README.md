# Challenge 3 – Predicción de Cancelación de Clientes (Churn)

## 📌 Objetivo
Analizar los datos de clientes de una empresa de telecomunicaciones, identificar los principales factores que influyen en la cancelación del servicio y construir modelos predictivos para anticipar el churn.  
Con base en los resultados, se proponen estrategias de retención.

---

## 🔎 Metodología
1. **Preprocesamiento de datos**
   - Eliminación de columnas irrelevantes (`customerID`).
   - Conversión de variables numéricas a formato adecuado (`Charges.Total`, `Charges.Monthly`).
   - Codificación de variables categóricas mediante *one-hot encoding*.
   - Balanceo de clases con **SMOTE**.
   - Escalado de datos con **StandardScaler** (para modelos sensibles a la escala).

2. **División de datos**
   - 70% entrenamiento  
   - 30% prueba  
   - Estratificación para mantener proporciones de clases.

3. **Modelos evaluados**
   - **Regresión Logística** (con normalización).  
   - **Random Forest** (sin normalización).

4. **Métricas utilizadas**
   - Exactitud (Accuracy)  
   - Precisión  
   - Recall  
   - F1-score  
   - Matriz de confusión

---

## 📊 Resultados de los modelos
**Regresión Logística**  
- Accuracy: 0.86  
- Recall clase 1 (canceló): 0.93  
- F1-score clase 1: 0.87  

**Random Forest**  
- Accuracy: 0.87  
- Recall clase 1 (canceló): 0.90  
- F1-score clase 1: 0.87  

**Conclusión:**  
Ambos modelos muestran un desempeño muy similar (F1 ≈ 0.87).  
- La **Regresión Logística** detecta mejor a los clientes que cancelan (mayor recall).  
- El **Random Forest** es más preciso al identificar cancelaciones (menor tasa de falsos positivos).

---

## 🔑 Factores que más influyen en la cancelación
- **Mayor probabilidad de cancelación:**
  - InternetService = Fiber optic  
  - PaymentMethod = Electronic check  
  - Cargos mensuales elevados (Charges.Monthly)  
  - Paperless Billing  
  - Senior Citizen  

- **Menor probabilidad de cancelación:**
  - Mayor antigüedad (tenure)  
  - Contrato de dos años (Contract = Two year)  
  - Uso de servicios de soporte y seguridad (Online Security, Tech Support)  

---

## 🎯 Estrategias de retención propuestas
1. **Incentivar contratos a largo plazo** con descuentos o beneficios exclusivos.  
2. **Revisar el método de pago Electronic check**, ofreciendo alternativas más seguras y cómodas.  
3. **Mejorar la experiencia de clientes con fibra óptica**, reforzando la calidad del servicio y soporte proactivo.  
4. **Diseñar planes personalizados para clientes con cargos altos**, ofreciendo bundles o paquetes más accesibles.  
5. **Promover servicios de soporte y seguridad**, ya que se asocian a menor churn.  
6. **Programas de fidelización temprana** para clientes en su primer año de permanencia.  

---

## 📂 Estructura del repositorio
- `notebooks/` → desarrollo del análisis y modelos en Google Colab.  
- `data/` → datasets utilizados (en caso de ser compartibles).  
- `README.md` → documentación del proyecto.  

---

## 🚀 Conclusión
El análisis permitió identificar los factores más relevantes en la cancelación y proponer acciones específicas de retención.  
El uso de modelos predictivos permite anticipar qué clientes tienen mayor probabilidad de cancelar y orientar los recursos de la empresa de manera más eficiente.
