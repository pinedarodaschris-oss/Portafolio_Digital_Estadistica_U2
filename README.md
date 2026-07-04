# Portafolio_Digital_Estadistica_U2
## Bitácora de Autoevaluación - Unidad 2

### Aprendizajes Logrados:
* Modelado y simulación de intervalos de confianza y pruebas paramétricas utilizando la abstracción avanzada de `scipy.stats`.
* Uso correcto del análisis de varianza (ANOVA) y pruebas Post-Hoc para evitar la inflación del error Tipo I en comparaciones múltiples.

### ⚠️ Principales Dificultades Algorítmicas Superadas:
* **Límite de Punto Flotante (OverflowError):** Identificación del colapso matemático al intentar procesar factoriales exactos en la distribución binomial con muestras masivas ($N=10.000$), justificando la necesidad de aplicar aproximaciones asintóticas mediante la distribución Normal ($Z$).
* **Limpieza de Datos Regionales:** Normalización y limpieza dimensional de vectores mediante dropna() para prevenir desajustes en el cálculo de sumas de cuadrados en las librerías estadísticas.
### 🧠 Reflexión Crítica:
* El desarrollo modular de esta unidad consolidó nuestra capacidad para transicionar desde la analítica descriptiva hacia la inferencia algorítmica estructurada. Evidenciamos que la significancia estadística (valor-$p$) no es un valor automatizado aislado, sino un modelo matemático gobernado por los grados de libertad y el tamaño de la muestra, indispensable para la toma de decisiones basada en evidencia dentro de nuestro proyecto integrador.
