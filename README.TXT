# ⚙️ Taller Práctico - Análisis de Rendimiento de Logs  
**Autor:** Yeison Andar Peñaranda  

---

## 🧠 ¿De qué trata este proyecto?

Este proyecto nació como un ejercicio práctico para aprender a **analizar el rendimiento de una aplicación web real** a partir de sus registros (logs).  
La idea es tomar los datos “crudos” que genera una app cuando recibe peticiones, procesarlos y descubrir qué tan bien está funcionando:  
qué tan rápido responde, cuántos errores lanza, y qué rutas son las más usadas o las más lentas.

Todo fue desarrollado en **Google Colab** usando **Python**, combinando análisis de datos, funciones lambda, visualización y algo de estadística.

---

## 🎯 Objetivo

El objetivo principal fue **detectar patrones y posibles problemas de rendimiento** en una aplicación web, a través de:

- Promedios y desviaciones de los tiempos de respuesta  
- Códigos de error más comunes  
- Identificación de peticiones lentas  
- Rutas y usuarios más activos  
- Comportamiento del sistema a lo largo del tiempo  

En otras palabras, entender si el sistema va fluido o si se está “ahogando” en ciertos puntos.

---

## 🧰 Herramientas que utilicé

- 🐍 **Python 3.8+**  
- 🧮 **Pandas** → para manejar y analizar los datos  
- 📊 **Matplotlib / Seaborn** → para graficar resultados  
- 📁 **JSON / CSV** → para exportar los análisis  
- ☁️ **Google Colab** → para escribir, ejecutar y documentar el proyecto

---

## 🧩 Estructura del proyecto


---

## 🔍 Qué hace el programa

### 1️⃣ Genera los logs
Primero se crea un archivo con más de **1000 registros simulados**.  
Cada línea incluye:  
- Fecha y hora  
- Nivel (INFO, DEBUG, WARN, ERROR)  
- Ruta solicitada  
- Tiempo de respuesta  
- Código HTTP  
- ID de usuario  
- Tamaño del payload  

### 2️⃣ Procesa y limpia los datos
Se leen los logs, se extrae la información importante y se organizan en un **DataFrame de Pandas**, para luego poder analizarlos con facilidad.

### 3️⃣ Analiza el rendimiento
Se obtienen estadísticas como:  
- Promedio y mediana de tiempos de respuesta  
- Percentiles (50, 75, 90, 95, 99)  
- Conteo de errores 4xx y 5xx  
- Promedio de tiempos por nivel de log  

### 4️⃣ Visualiza todo
Incluye gráficos creados con **Seaborn** y **Matplotlib** para interpretar los resultados de forma visual:

- 🔹 Tiempos promedios por nivel (gráfico de barras)  
- 🔹 Evolución del rendimiento (línea)  
- 🔹 Distribución de códigos HTTP (circular)  
- 🔹 Top rutas más lentas (barras horizontales)  
- 🔹 Dispersión de tiempos por nivel (boxplot logarítmico)

---

## 📊 Un vistazo rápido a los resultados

| Nivel | Registros | Promedio (ms) | Mediana (ms) | Máximo (ms) |
|:------|-----------:|--------------:|--------------:|-------------:|
| INFO  | 780 | 205.6 | 198 | 4100 |
| WARN  | 180 | 310.2 | 255 | 4200 |
| ERROR | 65  | 1250.9 | 985 | 4700 |

Los resultados muestran un comportamiento normal, pero con algunos picos que vale la pena analizar.

---

## 📈 Gráficos generados

Los gráficos ayudan a entender rápidamente qué está pasando:

- 📉 **Promedio de tiempo por nivel**  
- ⏱️ **Tendencia del rendimiento a lo largo del tiempo**  
- 🧩 **Distribución de códigos HTTP**  
- 🔥 **Boxplot con los outliers más lentos**  

*(Los gráficos se generan directamente desde el notebook en Colab.)*

---

## 💬 Conclusiones

Después del análisis, puedo decir que:

- El sistema tiene un rendimiento **estable**, aunque con picos en ciertas rutas.  
- Los niveles **WARN** y **ERROR** requieren atención, especialmente cuando el p95 supera los **1000 ms**.  
- El flujo de usuarios y rutas más activas está bien distribuido, pero se podría optimizar el manejo de errores.

En resumen, este tipo de análisis ayuda a **detectar cuellos de botella** antes de que se conviertan en un problema real.

---

## 🔮 Próximas mejoras

- Agregar alertas automáticas cuando haya tiempos anómalos  
- Incluir un modelo predictivo con Machine Learning  
- Crear visualizaciones interactivas (Plotly / Dash)  
- Integrar un panel de monitoreo en tiempo real con Grafana o Power BI  

---

## 👨‍💻 Sobre mí

Soy **Yeison Andar**, estudiante de Ingeniería de Software, apasionado por el desarrollo web y los proyectos que mezclan **datos, automatización y rendimiento**.  
Este trabajo forma parte de mi proceso de aprendizaje, pero también de mi gusto por **entender cómo funcionan las cosas detrás del código**.

📫 Si quieres ver más de mis proyectos:  
👉 [github.com/YeisonAndar](https://github.com/YeisonAndar)

---

## 🪪 Licencia

Este proyecto se distribuye bajo la licencia **MIT**, así que puedes usarlo, modificarlo o mejorarlo libremente, siempre dando el crédito correspondiente.

