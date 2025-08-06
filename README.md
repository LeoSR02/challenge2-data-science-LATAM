# 🧾 Proceso ETL y Análisis Exploratorio – Churn de Clientes | Telecom X

Este repositorio contiene el desarrollo completo del proceso ETL (Extracción, Transformación y Carga) y el análisis exploratorio de los datos de churn de clientes de la empresa  *Telecom X*.

---

## 🔄 Proceso ETL

### 1. 📥 Extracción

- Lectura directa del archivo `.json` desde un repositorio remoto:
  - URL: `https://raw.githubusercontent.com/LeoSR02/challenge2-data-science-LATAM/refs/heads/main/TelecomX_Data.json`

---

### 2. 🧹 Transformación

- **Normalización** de estructuras anidadas:
  - Columnas: `customer`, `phone`, `account`, `internet`.

- **Limpieza de datos**:
  - Conversión de tipos (`object` → `float`, object → `boolean` ).
  - Eliminación de columnas redundantes.
  - Verificación y tratamiento de valores nulos y duplicados.

- **Renombramiento y creación de nuevas variables**:
  - Ejemplo:  
    - `Cuentas_Diarias = Charges_Monthly / 30`

- **Conversión de variables categóricas a binarias**:
  - Ejemplo: `"Yes"` / `"No"` → `1` / `0`

- **Estandarización de valores**:
  - Limpieza y transformación de datos
  - Ejemplo: replace{
            'No phone service': 'No',
            'No internet service': 'No'}

---

### 3. 💾 Carga

- DataFrame final procesado:
  - `df_final1`

---

## 📈 Análisis Exploratorio

### 🔘 Proporción de churn

- Gráfico tipo torta que muestra la proporción entre:
  - Clientes que permanecen
  - Clientes que se dieron de baja
    ![Distribución de retiro/abandono (churn)](graficos/grafico1.png)

---

### 🔥 Heatmap de características categóricas

- Análisis cruzado de:
  - **Eje Y**: `Género + Tipo de contrato`
  - **Eje X**: `Tipo de servicio de internet`

- Visualización tipo semáforo:
  - Verde → baja evasión
  - Rojo → alta evasión

---

### 📊 Variables numéricas

- **Boxplots comparativos** para analizar:
  - `ChargesMonthly` → Clientes que se dieron de baja tienen gastos más altos.
  - `Tenure` → Clientes que permanecen tienen mayor tiempo de permanencia.

---


---

## 📁 Archivos Generados

- `Churn_de_Clientes.json` → Dataset procesado.
- `grafico_churn.png` → Gráfico de torta de churn.
- Gráficos de análisis visual se muestran inline en notebooks (no se exportan todos).

---
