
# Análisis de Series Temporales Jerárquicas para Motivos de Migración

## Descripción

En este repositorio se presenta una aplicación del modelo de series
temporales jerárquicas para el estudio de los motivos de la migración
utilizando datos de la Encuesta Nacional de Ocupación y Empleo (ENOE).
Los datos jerárquicos utilizados tienen tres niveles de desagregación:

- **Nivel 0**: Tasa de migración agregada.  
- **Nivel 1**: 5 tasas de migración a nivel regional.  
- **Nivel 2**: 32 tasas de migración a nivel ciudad.  
- **Nivel 3**: Descomposición de los 5 motivos de migración.

![](img/Región.png)

## Metodología

El enfoque de abajo hacia arriba (`bottom-up`) se empleó para trabajar
con 160 series de nivel inferior y, utilizando la matriz de sumas, se
agregaron los valores ajustados para obtener una tasa de migración
global ajustada.

Se utilizó también el enfoque de arriba hacia abajo (`top-down`) para
suavizar las series que contenían ruido en los niveles inferiores, lo
que condujo a mejores pronósticos.

## Conclusiones

1.  **Modelos Elegantes**: Los modelos de series temporales jerárquicas
    son herramientas elegantes para modelar y pronosticar series
    temporales con estructuras jerárquicas y datos funcionales.  
2.  **Suavización de Series**: Los modelos de arriba hacia abajo ayudan
    a suavizar series ruidosas en los niveles inferiores, mejorando los
    pronósticos.  
3.  **Datos Escasos**: Este tipo de modelo puede trabajar eficazmente
    incluso con pocos datos, proporcionando pronósticos confiables en
    los niveles de agregación.  
4.  **Limitaciones en Niveles Inferiores**: La distribución en los
    niveles más bajos no presentó una buena adecuación, mostrando un
    horizonte muy plano.  
5.  **Motivos Principales de Migración**: La mayor parte de las
    diferencias en el crecimiento demográfico de las ciudades y regiones
    en México se deben a la búsqueda de oportunidades de desarrollo
    económico y social, y un ambiente adecuado para mejorar la calidad
    de vida. Reunirse con familiares y trabajo son los principales
    motivos de desplazamiento, presentando mayor variabilidad en el
    tiempo.

## Resultados Empíricos

En comparación con los modelos ARIMA y Random Walk, muchos de los
resultados empíricos no fueron concluyentes para varios enfoques.

- Hierarquical Time Series:
  [Script](https://dvillasanao.github.io/Hierarchical_Time_Series/Hierarchical%20Time%20Series.nb.html)
- Cross Validation: [Script](Validación%20Cruzada.nb.html)

## Estructura del Repositorio

- `data/`: Contiene los datos utilizados en el análisis.  
- `scripts/`: Scripts de R utilizados para el análisis y modelado.  
- `results/`: Resultados del análisis, incluyendo gráficos y tablas.

## 📦 Instalación

Para instalar los paquetes necesarios en R, ejecutar:

``` r
install.packages(c("hts", "forecast", "dplyr", "ggplot2"))
```
