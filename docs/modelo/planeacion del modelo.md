# 📊 Flujo de Evolución del Modelo de Predicción de Eventos

Este documento describe la evolución paso a paso del modelo, iniciando con un **forecasting puro (baseline)** y avanzando hacia un **modelo híbrido** que incorpora más variables.

---

## 🔹 1. Baseline: Forecasting puro
Nuestro punto de partida será un modelo simple de predicción basado únicamente en variables temporales y de ubicación.

### Variables usadas:
- 🟦 `EVENTOS` → número de eventos (variable objetivo)
- 🟩 `ESTADO_DEPTO` → región/departamento
- 🟨 `MES`
- 🟨 `AÑO`

### Objetivo:
- Predecir el número de eventos futuros por región en un mes/año específico.
- Establecer un **baseline** (referencia inicial).

### Métricas de evaluación:
- 📏 **RMSE** (Root Mean Squared Error)  
- 📏 **MAE** (Mean Absolute Error)  
- 📏 **MAPE** (Mean Absolute Percentage Error)  

---

## 🔹 2. Expansión hacia un Modelo Híbrido
Luego de tener el baseline, expandimos el modelo para incluir más información.

### Variables adicionales:
- 👤 **Demográficas**
  - `SEXO`
  - `ETNIA`
  - `DISCAPACIDAD`
  - `CICLO_VITAL`

- ⏳ **Temporales**
  - `TRIMESTRES` (para capturar estacionalidad más amplia)

### Objetivo:
- Enriquecer la predicción con variables explicativas adicionales.
- Detectar patrones más finos (ej. diferencias entre grupos demográficos o ciclos trimestrales).

---

## 🔹 3. Comparación final
Una vez tengamos ambos modelos, los comparamos:

- 📌 **Forecasting puro (baseline)**  
  - Más simple y rápido.  
  - Menor capacidad explicativa.  

- 📌 **Forecasting híbrido (con demográficas + temporales)**  
  - Más complejo.  
  - Posible mejora en precisión y explicabilidad.  

### Resultado esperado:
- Determinar si el modelo híbrido ofrece una **mejora significativa** frente al baseline.  
- Decidir cuál utilizar según el **equilibrio entre simplicidad y precisión**.

---


# ❓ Preguntas que podemos responder con los modelos

A continuación se listan ejemplos de preguntas clave que se pueden abordar con el **forecasting puro (baseline)** y con el **modelo híbrido**.  
También se incluyen ejemplos de cómo redactar las respuestas de forma clara y útil.

---

## 🔹 1. Forecasting puro (baseline)

### Preguntas posibles:
- 📌 ¿Cuántos eventos se esperan en el departamento **Antioquia** en **junio de 2025**?
- 📌 ¿Cuál es la tendencia de eventos en el departamento **Valle del Cauca** para el próximo año?
- 📌 ¿Qué departamentos tienen una mayor proyección de crecimiento de eventos en 2026?

### Ejemplo de respuesta:
> ✅ **Respuesta (modelo baseline):**  
> Según el modelo de forecasting, se proyecta que en **Antioquia** ocurran **320 eventos en junio de 2025**.  
> La tendencia indica un **crecimiento moderado del 5% anual**, concentrado principalmente en la segunda mitad del año.

---

## 🔹 2. Forecasting híbrido (con variables adicionales)

### Preguntas posibles:
- 👤 ¿Existen diferencias en el número de eventos proyectados entre **hombres y mujeres** en el departamento **Cauca** durante 2025?
- 👤 ¿Qué grupos etarios (ciclo vital) muestran mayor vulnerabilidad en términos de eventos proyectados en 2026?
- ⏳ ¿Hay patrones estacionales por **trimestres** que afecten la distribución de eventos en **Bogotá**?
- 🌍 ¿Qué combinación de variables (género, etnia, trimestre) explica mejor la variación en el número de eventos en 2024?

### Ejemplo de respuesta:
> ✅ **Respuesta (modelo híbrido):**  
> En el departamento **Cauca**, el modelo híbrido proyecta que durante **2025** los **hombres representarán el 60% de los eventos**, mientras que las mujeres el **40%**.  
> Además, se observa que los eventos tienden a concentrarse en el **segundo trimestre**, lo cual sugiere un componente estacional importante.  
> Este patrón no fue visible en el forecasting puro, lo que resalta la utilidad del modelo híbrido.

---

## 🔹 3. Comparación de respuestas

- 🔎 **Baseline:** ofrece predicciones generales por tiempo y región.  
- 🔎 **Híbrido:** permite profundizar en **qué factores explican** los cambios y cómo se distribuyen entre distintos grupos poblacionales.  

Ejemplo de cómo resumir la comparación:
> 📊 **Conclusión:**  
> Mientras que el baseline proyecta **320 eventos en Antioquia en junio de 2025**,  
> el híbrido aclara que el **55% de esos eventos corresponderán a población joven** y que la mayor incidencia se dará en el **segundo trimestre del año**.
