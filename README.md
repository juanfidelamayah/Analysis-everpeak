# Analysis-everpeak
Análisis Exploratorio de Datos y Segmentación de Clientes
Este repositorio contiene el pipeline completo de procesamiento, limpieza, análisis exploratorio de datos (EDA) y segmentación de la base de usuarios de ConnectaTel. El objetivo del proyecto es identificar patrones de consumo, corregir inconsistencias en los datos y generar hallazgos estratégicos para optimizar la oferta comercial de la compañía.

Pasos Realizados en el Proyecto
1. Carga e Inspección Inicial de Datos
Carga de Datasets: Importación y unificación de las fuentes de información operativas (users, calls, messages).

Diagnóstico de Estructura: Revisión de dimensiones, nombres de columnas, presencia de valores nulos y verificación de tipos de datos (dtypes).

2. Limpieza y Preparación de Datos
Estandarización de Tipos de Datos: Conversión de variables numéricas almacenadas como texto (object) a formato cuantitativo mediante pd.to_numeric.

Tratamiento de Nulos y Faltantes: Imputación de valores ausentes con 0 en las métricas de consumo de llamadas y mensajes para mantener la integridad de las filas.

Consolidación de Métricas (merge): Agregación de tráfico por usuario (usage_agg) y unión con el perfil general para consolidar el DataFrame final user_profile.

Renombrado Definitivo de Columnas: Estandarización de nombres de variables finales (age, total_messages, total_calls, total_call_minutes, plan).

3. Análisis Exploratorio y Visualización (EDA)
Análisis de Distribuciones: Generación de diagramas de caja (boxplots) condicionados por tipo de plan para comparar la variabilidad de consumo entre planes Básico y Premium.

Identificación de Outliers: Diagnóstico de valores atípicos en consumo mediante la regla del Rango Intercuartílico (IQR=Q 
3 −Q1).

Evaluación de Mantenimiento de Outliers: Justificación analítica de conservar los consumos atípicos superiores (heavy users) por representar comportamientos reales de facturación y demanda de red.

4. Segmentación de Clientes (Feature Engineering)
Segmentación por Nivel de Uso (grupo_uso): Clasificación lógica de usuarios según su frecuencia de llamadas y envío de mensajes:

Bajo uso: < 5 llamadas y < 5 mensajes.

Uso medio: < 10 llamadas y < 10 mensajes.

Alto uso: Todos los demás casos.

Segmentación por Edad (grupo_edad): Categorización demográfica en tres grandes grupos:

Joven: < 30 años.

Adulto: de 30 a 59 años.

Adulto Mayor: 60+ años.

5. Visualización de Segmentos
Análisis Frecuencial: Generación de gráficos de barras (sns.countplot) ordenados por categoría para analizar el volumen absoluto y relativo de usuarios en cada segmento de uso y edad.

6. Análisis Ejecutivo y Recomendaciones de Negocio
Evaluación de Impacto: Traducibilidad de los hallazgos en recomendaciones comerciales para la creación de nuevos planes tarifarios y estrategias de retención diferenciadas.

Tecnologías Utilizadas
Lenguaje: Python 3.x

Librerías Principales: pandas, numpy, matplotlib, seaborn

Entorno: Jupyter Notebook / Google Colab
