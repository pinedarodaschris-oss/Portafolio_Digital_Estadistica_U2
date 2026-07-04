# 🧩 Unidad 2: Inferencia Estadística y Modelado Algorítmico  

---

## 📊 Distribuciones Muestrales e Intervalos de Confianza (APE 06 - APE 09)
> Estudio de estimadores puntuales, variabilidad muestral y construcción de intervalos de confianza ($Z$ y $T$ de Student) aplicados a la epidemiología.

* [Guía APE 06: Distribuciones Muestrales](./Guias_Laboratorio_Corregidas/APE_06_Distribuciones_Muestrales.pdf)
* [Guía APE 07: Estimación Puntual](./Guias_Laboratorio_Corregidas/APE_07_Estimacion_Puntual.pdf)
* [Guía APE 08: Intervalos de Confianza](./Guias_Laboratorio_Corregidas/APE_08_Intervalos_Confianza.pdf)
* [Guía APE 09: Modelado de Intervalos en Loja](./Guias_Laboratorio_Corregidas/APE_009_Intervalos%20(1).pdf)

---

## ⚖️ Pruebas de Hipótesis y Comparación de Grupos (APE 10 - APE 11)
> Diseño de contrastes paramétricos unimuestrales y análisis de variabilidad múltiple mediante algoritmos de ANOVA de 1 Factor.

* [Guía APE 10: Pruebas de Hipótesis Paramétricas](./Guias_Laboratorio_Corregidas/APE010_Interferencia_EstadisticaPruebas_deHip%C3%B3tesis_Param%C3%A9tricas_(Z_y_T)_y%20An%C3%A1lisisdel_Valor-p.pdf)
* [Guía APE 11: Análisis de Varianza (ANOVA)](./Guias_Laboratorio_Corregidas/APE_11_Varianza(ANOVA).pdf)

---

## 🧪 Evaluación Sumativa Final: Inferencia en Casos de Dengue (Región Loja)  
> Hito integrador del PID-2025 que aplica las fronteras de la inferencia estadística sobre el dataset real del MSP.

* [Cuaderno de Código en Google Colab (.ipynb)](./Evaluacion_Sumativa_Final/Evaluacion_Sumativa_Final_Dengue_Loja.ipynb)
* [Fuente de Datos (Dataset CSV)](./Evaluacion_Sumativa_Final/Datos_Dengue_MSP_Ene2021_Ago2025.csv)

### 📌 Descripción del Problema  
Contraste de la media de casos de Dengue por registro en Loja frente a un parámetro teórico mediante una prueba $T$ unimuestral, seguido de un análisis de varianza (ANOVA de 1 factor) para determinar si existen diferencias significativas en las medias de contagio entre los cantones con mayor densidad de reportes de la provincia.

### 📊 Formulación Matemática de las Hipótesis

**Contraste Unimuestral (Edad/Casos):**
* $H_0: \mu = 2$ 
* $H_1: \mu \neq 2$

**Comparación de Grupos (Cantones):**
* $H_0: \mu_{\text{Canton1}} = \mu_{\text{Canton2}} = \dots = \mu_{\text{CantonK}}$
* $H_1: \exists \, i, j \quad \text{tal que} \quad \mu_i \neq \mu_j$

### 💻 Fragmento de Implementación Crítica
```python
# Abstracción avanzada con scipy.stats para ANOVA de 1 Factor
f_statistic, p_value_anova = stats.f_oneway(*grupos_anova)
print(f"Estadístico F: {f_statistic:.4f} | Valor p (ANOVA): {p_value_anova:.4f}")

# Algoritmo Post-Hoc de Tukey HSD para control del Error Tipo I
tukey_result = pairwise_tukeyhsd(endog=data_for_tukey['Total_Cases'],
                                 groups=data_for_tukey['Canton'],
                                 alpha=0.05)
