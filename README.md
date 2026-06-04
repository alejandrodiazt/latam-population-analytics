# Análisis demográfico y modelado de crecimiento poblacional en América Latina

Este repositorio contiene el módulo analítico desarrollado para el procesamiento, modelado predictivo y segmentación no supervisada de las tendencias demográficas en América Latina desde 1960 hasta 2023. El proyecto implementa una metodología estructurada de ciencia de datos para identificar patrones macroeconómicos y de planificación social en la región.

## Características del proyecto

*   **Análisis exploratorio (EDA)**: Filtrado, limpieza y reestructuración de matrices de datos transaccionales de formato ancho (*wide*) a formato largo (*long*) para 19 economías latinoamericanas.
*   **Ingeniería de características**: Cálculo indexado de métricas avanzadas como el Crecimiento Absoluto, Factor de Crecimiento Estructurado y la Tasa de Crecimiento Anual Compuesta (CAGR).
*   **Modelado predictivo**: Comparación empírica entre modelos de Regresión Lineal y Regresión Polinomial (Grado 2) para la proyección demográfica de largo plazo (Horizonte 2040).
*   **Segmentación no supervisada**: Agrupación de países por dinámicas de transición demográfica utilizando el algoritmo K-Means, optimizado mediante el Método del Codo y validado con Coeficientes de Silueta.
*   **Visualización dinámica**: Generación de mapas coropléticos interactivos y matrices de correlación temporal.

## Estructura del repositorio

```text
├── PipelineCRISP-DM.py            # Archivo principal de ejecución (Pipeline de Ciencia de Datos)
├── .gitignore              # Archivo de exclusión de datos masivos
└── README.md               # Documentación técnica del proyecto
```

Nota: El archivo origen de datos macroeconómicos del Banco Mundial (API_SP.POP.TOTL_DS2_es_csv_v2_16699 (3).csv) está excluido del control de versiones por diseño.

## Evaluación de modelos y resultados 
Módulo de regresión (Caso de estudio: Brasil)
El comportamiento curvilíneo de la aceleración demográfica fue evaluado mediante dos aproximaciones estadísticas:
Regresión lineal: $R^2 = 0.9916$
Regresión polinomial (Grado 2): $R^2 = 0.9976$
El ajuste polinomial minimiza significativamente el Error Cuadrático Medio (MSE), capturando con precisión matemática la desaceleración marginal reciente.

## Módulo de clustering
La optimización del hiperparámetro $k$ mediante el método del codo determinó un entorno ideal de $k=3$ clústeres, con un Coeficiente de Silueta global de 0.5711, lo que valida una separación inter-clúster robusta:

Clúster 0 (Crecimiento acelerado): Países con bases poblacionales históricas bajas pero factores de expansión masivos (v.g., Colombia, Perú, Guatemala). CAGR promedio: 2.15%.

Clúster 1 (Gigantes regionales): Economías con alta densidad demográfica inicial y volumen absoluto dominante, pero estabilización indexada (Brasil y México). CAGR promedio: 1.89%.

Clúster 2 (Transición demográfica avanzada): Países de crecimiento lento, estable y curvas de envejecimiento prematuro (Argentina, Chile, Uruguay, Cuba). CAGR promedio: 1.04%.

## Requisitos del sistema
Entorno de ejecución configurado bajo Python 3.10+ con las siguientes dependencias base:
pip install pandas numpy scikit-learn matplotlib seaborn plotly
