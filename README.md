# Análisis de Ventas y Éxito de Videojuegos – Ice

[![Licencia MIT](https://img.shields.io/badge/Licencia-MIT-blue.svg)](LICENSE)
[![Python Version](https://img.shields.io/badge/Python-3.x-blue.svg)](https://www.python.org/)

## Descripción del Proyecto
El presente trabajo analiza los datos de la tienda online **Ice**, que vende videojuegos alrededor del mundo. El objetivo es identificar cuáles juegos resultan exitosos y cuáles no, para tomar decisiones estratégicas en futuros proyectos y campañas de marketing.

## Contenido
- [Inicialización](#inicialización)
- [Descripción y Validación de los Datos](#descripción-y-validación-de-los-datos)
- [Preprocesamiento y Enriquecimiento](#preprocesamiento-y-enriquecimiento)
- [Análisis de Datos](#análisis-de-datos)
  - [Análisis por Años](#análisis-por-años)
  - [Ventas por Plataforma](#ventas-por-plataforma)
- [Conclusiones](#conclusiones)
- [Aplicaciones en Negocios y Finanzas](#aplicaciones-en-negocios-y-finanzas)
- [Instalación y Uso](#instalación-y-uso)
- [Contribución](#contribución)
- [Licencia](#licencia)
- [Contacto](#contacto)

---

## Inicialización
En esta primera etapa se realizan los siguientes procesos:
1. Cargar las librerías necesarias para el análisis (pandas, numpy, matplotlib, seaborn, scipy).
2. Importar el dataset `games.csv`, que contiene información de videojuegos (nombre, plataforma, año de lanzamiento, género, ventas en distintas regiones, puntajes de críticos y usuarios, etc.).
3. Revisar y familiarizarse con los datos para determinar qué procesos de limpieza y enriquecimiento son necesarios.

---

## Descripción y Validación de los Datos
El dataset contiene 6,701 filas y 11 columnas. Se observan columnas como:
- **Name**: Nombre del juego.
- **Platform**: Plataforma en la que se lanzó el juego.
- **Year_of_Release**: Año de lanzamiento.
- **Genre**: Género del juego.
- **NA_sales**, **EU_sales**, **JP_sales**, **Other_sales**: Ventas en distintas regiones (en millones).
- **Critic_Score** y **User_Score**: Puntuaciones dadas por críticos y usuarios.
- **Rating**: Clasificación del juego.

Se han detectado valores faltantes en algunas columnas (por ejemplo, en *user_score*, *critic_score* y *rating*), los cuales se abordan en el proceso de preprocesamiento.

---

## Preprocesamiento y Enriquecimiento
Las tareas realizadas para preparar los datos incluyen:

1. **Revisión de Valores Faltantes:**  
   - Se identificaron entradas con valores `NaN` o etiquetas como `"tbd"` en *user_score*.  
   - Se procedió a reemplazar o conservar estos valores según la importancia de cada columna para no distorsionar el análisis.

2. **Ajuste de Nombres de Columnas:**  
   - Se estandarizaron los nombres de las columnas (por ejemplo, pasándolos a minúsculas) para facilitar la manipulación y análisis posterior.

3. **Creación de una Nueva Columna de Ventas Totales:**  
   - Se insertó la columna `total_sales` calculada como la suma de las ventas en Norteamérica, Europa, Japón y otras regiones. Esto facilita la evaluación global del éxito de cada juego.

4. **Validación de Datos:**  
   - Se verificó que no existan entradas duplicadas o inconsistentes que puedan afectar los resultados del análisis.

---

## Análisis de Datos

### Análisis por Años
Se ha agrupado el dataset por *year_of_release* para analizar la cantidad de juegos lanzados cada año.  
- **Visualización:**  
  Un gráfico de barras muestra la evolución anual en la cantidad de lanzamientos, permitiendo identificar tendencias y posibles periodos de mayor actividad en la industria.

### Ventas por Plataforma
Se analizaron las ventas totales por plataforma:
- **Pivot Table:**  
  Se creó una tabla pivote que agrupa las ventas totales de cada plataforma por año.
- **Gráficos Comparativos:**  
  Se generaron gráficos de barras y líneas para visualizar tanto la cantidad de lanzamientos por plataforma como la evolución de las ventas a lo largo de los años.  
- **Top 10 Plataformas:**  
  Se identificaron las 10 plataformas con mayores ventas totales, lo que permite focalizar estrategias de marketing y análisis de tendencias de consumo.

---

## Conclusiones
- **Ajuste de Datos:**  
  Se ajustaron los nombres de columnas y se trataron los valores faltantes en *year_of_release*, *critic_score*, *user_score* y *rating*.  
- **Ventas Totales:**  
  La creación de la columna `total_sales` permitió una mejor comprensión del rendimiento de cada juego en el mercado global.  
- **Tendencias de Lanzamientos y Ventas:**  
  El análisis por años y por plataformas muestra tendencias importantes que pueden guiar decisiones estratégicas, como el enfoque en determinadas plataformas o el ajuste en campañas promocionales según la época de lanzamiento.

---

## Aplicaciones en Negocios y Finanzas
Las técnicas de análisis aplicadas en este proyecto tienen múltiples aplicaciones en otros contextos:
- **Estrategia de Producto:**  
  Identificar tendencias de éxito en el lanzamiento de productos permite planificar futuras campañas y lanzamientos.
- **Análisis de Rentabilidad:**  
  La evaluación de ventas totales por región y plataforma es esencial para determinar la rentabilidad y asignar presupuestos en marketing.
- **Optimización de Recursos:**  
  Los insights obtenidos a partir de datos históricos ayudan a prever demandas y ajustar inversiones en desarrollo y promoción.
- **Toma de Decisiones Basada en Datos:**  
  La integración de análisis estadístico y visualización facilita la identificación de patrones y la formulación de estrategias financieras y comerciales.

---

## Instalación y Uso

### Requisitos
- Python 3.x
- pandas, numpy, matplotlib, seaborn, scipy

### Pasos para Ejecutar el Proyecto
1. **Clonar el repositorio:**
   ```bash
   git clone https://github.com/tu_usuario/ice-games-analysis.git
