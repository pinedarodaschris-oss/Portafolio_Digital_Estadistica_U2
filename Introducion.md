# 🧩 Unidad 2: Inferencia Estadística y Modelado Algorítmico (Grupo D)

---

## 📊 Distribuciones Muestrales e Intervalos de Confianza (APE 06 - APE 09)
> Análisis de estimadores puntuales, error estándar y simulación de intervalos de confianza ($Z$ y $T$ de Student) sobre modelos analíticos.

* [Guía APE 07: Estimación Puntual](./Guias_Laboratorio_Corregidas/APE_007_Normal.ipynb)
* [Guía APE 08: Intervalos de Confianza](./Guias_Laboratorio_Corregidas/APE_008_TLC.ipynb)
* [Guía APE 09: Modelado de Intervalos en Loja](./Guias_Laboratorio_Corregidas/APE_009_Intervalos.ipynb)

---

## ⚖️ Pruebas de Hipótesis y Comparación de Grupos (APE 10 - APE 11)
> Parametrización de contrastes de hipótesis unimuestrales, control del error Alfa y análisis de variabilidad múltiple.

* [Guía APE 10: Pruebas de Hipótesis Paramétricas y Valor-p](./Guias_Laboratorio_Corregidas/APE010_Interferencia_EstadisticaPruebas_deHipótesis_Paramétricas_(Z_y_T)_yAnálisisdel.ipynb).
* [Guía APE 11: Análisis de Varianza (ANOVA) y Post-Hoc](./Guias_Laboratorio_Corregidas/APE_11_Varianza(ANOVA).ipynb)

---

## 🧪 Evaluación Sumativa Final: Inferencia en Casos de Dengue (Región Loja)
> Componente práctico e hito integrador del PID-2025 que evalúa el comportamiento epidemiológico regional del MSP.

* [Cuaderno de Código en Google Colab (.ipynb)](./Evaluacion_Sumativa_Final/Evaluacion_Sumativa_Final_Dengue_Loja.ipynb)
* [Fuente de Datos (Dataset Excel Original)](./Evaluacion_Sumativa_Final/Datos_Dengue_MSP_Ene2021_Ago2025.xlsx)

### 📌 Descripción del Problema
Contraste de la media de casos de Dengue por registro en la provincia de Loja frente a un parámetro teórico mediante una prueba $T$ unimuestral, acoplado a un Análisis de Varianza (ANOVA de 1 factor) para determinar si existen discrepancias significativas entre las medias de contagio de los cantones con mayor volumen de reporte en la región.

### 📊 Formulación Matemática de las Hipótesis

**1. Contraste Unimuestral (Casos Totales):**
* $$H_0: \mu = 2$$
* $$H_1: \mu \neq 2$$

**2. Análisis de Varianza (Cantones Independientes):**
* $$H_0: \mu_{\text{Canton1}} = \mu_{\text{Canton2}} = \dots = \mu_{\text{CantonK}}$$
* $$H_1: \exists \, i, j \quad \text{tal que} \quad \mu_i \neq \mu_j$$

### 💻 Programa (Implementación Crítica en Python)
```python
# Contraste t de una muestra mediante scipy.stats
t_statistic, p_value = stats.ttest_1samp(total_cases_loja, mu_hipotetica)

# ANOVA de un factor para subgrupos de cantones seleccionados
f_statistic, p_value_anova = stats.f_oneway(*grupos_anova)

# Ajuste Post-Hoc de Tukey HSD para el control de la inflación del error Tipo I
tukey_result = pairwise_tukeyhsd(endog=data_for_tukey['Total_Cases'],
                                 groups=data_for_tukey['Canton'],
                                 alpha=0.05)
