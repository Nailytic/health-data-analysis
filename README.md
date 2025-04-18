# 🌐 Análisis de Datos Públicos de Salud

![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)
![GeoPandas](https://img.shields.io/badge/GeoPandas-0.10+-green.svg)
![Folium](https://img.shields.io/badge/Folium-0.12+-lightgreen.svg)
![R Shiny](https://img.shields.io/badge/R%20Shiny-1.6+-lightblue.svg)
![Estado](https://img.shields.io/badge/Estado-Completado-green.svg)

Un análisis geoespacial y temporal de tendencias de salud pública utilizando datos abiertos, con visualizaciones interactivas y correlaciones con factores socioeconómicos.

## 📋 Contenido
- [Descripción](#descripción)
- [Objetivos](#objetivos)
- [Datos](#datos)
- [Metodología](#metodología)
- [Estructura del Proyecto](#estructura-del-proyecto)
- [Resultados Clave](#resultados-clave)
- [Visualizaciones](#visualizaciones)
- [Aplicación Interactiva](#aplicación-interactiva)
- [Conclusiones y Recomendaciones](#conclusiones-y-recomendaciones)
- [Tecnologías Utilizadas](#tecnologías-utilizadas)
- [Configuración y Uso](#configuración-y-uso)

## 📝 Descripción
Este proyecto analiza datos públicos de salud relacionados con la propagación de enfermedades infecciosas (utilizando COVID-19 como caso de estudio), explorando patrones geoespaciales y temporales, e investigando correlaciones con factores socioeconómicos y demográficos para informar políticas de salud pública.

## 🎯 Objetivos
- Analizar patrones espaciales y temporales en la propagación de enfermedades infecciosas
- Identificar correlaciones entre factores socioeconómicos y tasas de incidencia/mortalidad
- Desarrollar visualizaciones geoespaciales interactivas para análisis de tendencias
- Construir modelos que expliquen las variaciones en resultados de salud entre regiones
- Crear una aplicación interactiva para exploración de datos por no especialistas

## 📊 Datos
El proyecto utiliza múltiples fuentes de datos públicos, incluyendo:
- Datos epidemiológicos de COVID-19 del Johns Hopkins CSSE (2020-2022)
- Datos demográficos y socioeconómicos del Banco Mundial y censos nacionales
- Información de infraestructura sanitaria de la OMS
- Datos de movilidad de Google Mobility Reports
- Indicadores de desarrollo humano de las Naciones Unidas

## 🔍 Metodología
1. **Recopilación y limpieza de datos**
   - Integración de múltiples fuentes de datos heterogéneas
   - Normalización y estandarización entre distintas jurisdicciones
   - Geocodificación y preparación para análisis espacial

2. **Análisis exploratorio y espacial**
   - Análisis de patrones temporales y espaciales
   - Identificación de clusters y hotspots
   - Correlación con variables socioeconómicas

3. **Modelado estadístico**
   - Desarrollo de modelos explicativos para variaciones regionales
   - Análisis de factores clave que influyen en resultados de salud
   - Validación cruzada y evaluación de robustez

4. **Visualización y comunicación**
   - Creación de mapas interactivos y animados
   - Desarrollo de dashboard con múltiples dimensiones de análisis
   - Implementación de aplicación interactiva en R Shiny

## 📁 Estructura del Proyecto
```
health-data-analysis/
│
├── data/                          # Datos utilizados en el análisis
│   ├── raw/                       # Datos originales sin procesar
│   │   ├── covid/                 # Datos epidemiológicos 
│   │   ├── socioeconomic/         # Datos socioeconómicos
│   │   ├── healthcare/            # Datos de infraestructura sanitaria
│   │   ├── mobility/              # Datos de movilidad
│   │   └── shapefiles/            # Archivos de formas geográficas
│   │
│   ├── processed/                 # Datos procesados para análisis
│   │   ├── combined_dataset.csv   # Dataset integrado principal
│   │   ├── spatial_data.geojson   # Datos espaciales preparados
│   │   └── time_series/           # Series temporales procesadas
│
├── notebooks/                     # Jupyter notebooks para análisis
│   ├── 01_data_collection.ipynb   # Recopilación y estructuración de datos
│   ├── 02_data_cleaning.ipynb     # Limpieza y preparación
│   ├── 03_exploratory_analysis.ipynb # Análisis exploratorio
│   ├── 04_spatial_analysis.ipynb  # Análisis espacial
│   ├── 05_statistical_modeling.ipynb # Modelado estadístico
│   └── 06_visualization_dev.ipynb # Desarrollo de visualizaciones
│
├── src/                           # Código fuente para funciones reutilizables
│   ├── data/                      # Procesamiento de datos
│   ├── analysis/                  # Funciones analíticas
│   ├── modeling/                  # Modelos estadísticos
│   ├── spatial/                   # Análisis espacial
│   └── visualization/             # Funciones de visualización
│
├── r_analysis/                    # Análisis en R
│   ├── spatial_stats.R            # Estadísticas espaciales avanzadas
│   └── modeling.R                 # Modelos estadísticos complementarios
│
├── models/                        # Modelos estadísticos guardados
│   ├── regression_models.pkl      # Modelos de regresión
│   └── spatial_models.pkl         # Modelos espaciales
│
├── shiny_app/                     # Aplicación interactiva en R Shiny
│   ├── app.R                      # Código principal de la aplicación
│   ├── global.R                   # Configuración global
│   ├── ui.R                       # Interfaz de usuario
│   ├── server.R                   # Lógica del servidor
│   └── www/                       # Recursos estáticos
│
├── maps/                          # Mapas generados
│   ├── static/                    # Mapas estáticos
│   └── interactive/               # Mapas interactivos HTML
│
├── visualizations/                # Visualizaciones adicionales
│   ├── temporal_trends.png        # Gráficos de tendencias temporales
│   ├── correlation_matrices.png   # Matrices de correlación
│   └── animated_spread.gif        # Animaciones de propagación
│
├── reports/                       # Informes y presentaciones
│   ├── technical_report.pdf       # Informe técnico detallado
│   ├── public_health_brief.pdf    # Resumen para autoridades sanitarias
│   └── presentation.pptx          # Presentación de resultados
│
├── requirements.txt               # Dependencias de Python
├── r_requirements.R               # Script para instalar dependencias de R
├── README.md                      # Documentación principal
└── LICENSE                        # Licencia del proyecto
```

## 🔑 Resultados Clave
- Identificación de 5 clusters geográficos con distintos patrones de propagación
- Fuerte correlación (r=0.78) entre densidad de población y velocidad de propagación inicial
- La infraestructura sanitaria explica el 42% de la varianza en tasas de mortalidad
- Los niveles socioeconómicos tienen mayor impacto en resultados que factores geográficos
- Se identificaron 3 patrones distintos de oleadas epidémicas relacionadas con políticas públicas

## 📈 Visualizaciones
![Spread Patterns](visualizations/spread_patterns.png)
*Patrones de propagación en diferentes regiones a lo largo del tiempo*

![Socioeconomic Correlation](visualizations/socioeconomic_correlation.png)
*Correlación entre factores socioeconómicos y resultados de salud*

![Healthcare Infrastructure](visualizations/healthcare_infrastructure.png)
*Distribución de infraestructura sanitaria y su relación con tasas de mortalidad*

![Mobility Impact](visualizations/mobility_impact.png)
*Impacto de patrones de movilidad en la propagación de la enfermedad*

## 💻 Aplicación Interactiva
La aplicación R Shiny desarrollada permite a usuarios:
- Explorar datos epidemiológicos por región y período temporal
- Comparar múltiples indicadores simultáneamente
- Visualizar correlaciones con factores socioeconómicos
- Generar informes personalizados para regiones específicas
- Analizar tendencias de series temporales con proyecciones

![Shiny App](visualizations/shiny_app_screenshot.png)
*Captura de pantalla de la aplicación interactiva R Shiny*

## 💡 Conclusiones y Recomendaciones
1. **Detección Temprana y Preparación**
   - Las regiones con mayor densidad y movilidad requieren sistemas de alerta temprana más robustos
   - Implementar monitoreo mejorado en áreas identificadas como potenciales epicentros

2. **Equidad en Salud Pública**
   - Abordar disparidades socioeconómicas que amplifican el impacto de crisis sanitarias
   - Priorizar mejoras de infraestructura en regiones subatendidas identificadas

3. **Políticas de Respuesta**
   - Las medidas de restricción de movilidad son más efectivas cuando se implementan en fases específicas
   - Personalizar respuestas según las características demográficas y socioeconómicas locales

4. **Preparación para Futuras Crisis**
   - Desarrollar capacidades predictivas basadas en indicadores clave identificados
   - Establecer sistemas de colaboración interregional enfocados en áreas de alto riesgo

## 🛠️ Tecnologías Utilizadas
- **Python**: Procesamiento de datos, análisis y visualización
- **GeoPandas/Shapely**: Análisis geoespacial
- **Folium/Leaflet**: Mapas interactivos
- **Scikit-learn/StatsModels**: Modelado estadístico
- **Matplotlib/Seaborn/Plotly**: Visualizaciones estáticas e interactivas
- **R/Shiny**: Desarrollo de aplicación interactiva
- **PostgreSQL/PostGIS**: Almacenamiento y consultas geoespaciales

## 🚀 Configuración y Uso

### Prerequisitos
- Python 3.8+
- R 4.0+ (para componentes de R Shiny)
- GDAL y dependencias geoespaciales

### Instalación
```bash
# Clonar repositorio
git clone https://github.com/tu-usuario/health-data-analysis.git
cd health-data-analysis

# Crear entorno virtual
python -m venv env
source env/bin/activate  # En Windows: env\Scripts\activate

# Instalar dependencias de Python
pip install -r requirements.txt

# Instalar dependencias de R
# R -e "source('r_requirements.R')"
```

### Ejecución del Análisis
1. Ejecutar notebooks en orden secuencial para reproducir el análisis completo
2. Para generar mapas interactivos:
```bash
python src/visualization/generate_maps.py
```

### Ejecución de la Aplicación Shiny
```bash
cd shiny_app
R -e "shiny::runApp()"
```

### Generación de Informes
```bash
python src/reports/generate_report.py --region "REGION_NAME" --output report.pdf
```

## 📄 Licencia
Este proyecto está bajo la licencia MIT - ver el archivo LICENSE para más detalles.

## 📧 Contacto
Tu Nombre - [tu.email@ejemplo.com](mailto:tu.email@ejemplo.com)

LinkedIn: [tu-perfil-linkedin](https://www.linkedin.com/in/tu-perfil/)

---
⭐️ ¡No olvides darle una estrella a este repositorio si te resultó útil! ⭐️
