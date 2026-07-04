# Portafolio_Digital_Estadistica_U2
## Bitácora de Autoevaluación - Unidad 2

### Aprendizajes Logrados:
* Modelado y simulación de intervalos de confianza y pruebas paramétricas utilizando la abstracción avanzada de `scipy.stats`.
* Uso correcto del análisis de varianza (ANOVA) y pruebas Post-Hoc para evitar la inflación del error Tipo I en comparaciones múltiples.

### Dificultades Algorítmicas Superadas:
* **Manejo de Desbordamiento Numérico (OverflowError):** Aprendimos que al calcular probabilidades exactas con factoriales en la distribución binomial con $N$ muy altos ($N=10000$), Python genera desbordamientos de punto flotante. Esto justificó formalmente la adopción y programación de aproximaciones por la distribución Normal ($Z$).
* **Limpieza de Datos Regionales:** Filtrado dinámico de cadenas y tratamiento de nulos (`dropna`) en las variables geográficas y cuantitativas para que `statsmodels` ejecutara las matrices de diseño sin errores estructurales.
