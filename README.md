# 🚀 Predicción de Adopción de Nuevo SKU

## 📌 Objetivo del Proyecto
Este modelo predice la **propensión a la adopción** de un nuevo producto promocionado en el **Mes 5** de campaña. El objetivo es identificar qué cuentas alcanzarán el target del **70% de adopción** basándose en su comportamiento histórico de ventas.

## 🛠️ El Problema de Datos
Los datos originales presentaban unidades en filas separadas por SKU. Se implementó un proceso de **Pivoting** para consolidar la información por cuenta y mes, transformando un formato largo a uno ancho apto para Machine Learning.

## 🧠 Metodología
* **Modelo:** Random Forest Regressor (Optimizado vía GridSearchCV).
* **Variables Clave (Features):**
    * Ventas totales históricas (2024 y 2025).
    * Ubicación geográfica (Region y Sector).
    * Tiempo de maduración (Meses en promoción).
* **Variable Objetivo (Target):** Adopción calculada como:
  $$Adopcion = \frac{Unidades\_Promo}{Unidades\_Promo + \times Unidades\_Antiguo}$$

## 📈 Resultados
* **MAE (Error Medio Absoluto):** 0.1598 (Margen de error del ~16% en la predicción de adopción).
* **Insights:** El volumen histórico de ventas en 2025 es el principal predictor de la velocidad de adopción del nuevo SKU.
