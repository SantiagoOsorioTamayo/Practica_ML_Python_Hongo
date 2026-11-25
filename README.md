# Clasificación de hongos comestibles y venenosos con Machine Learning

Proyecto del diplomado de Analítica de Datos e Inteligencia Artificial. Clasifica hongos como comestibles o venenosos a partir de 22 características categóricas (forma y color del sombrero, olor, tipo de laminillas, hábitat, etc.) usando un árbol de decisión.

## Datos
- Dataset: Mushroom, descargado desde OpenML con `fetch_openml` (originalmente del UCI Machine Learning Repository). No es necesario adjuntar ningún archivo.
- 8.124 registros, 22 variables predictoras categóricas y la variable objetivo `class`.
- Clases: `e` (comestible, 4.208 registros) y `p` (venenoso, 3.916 registros).

## Metodología
1. Carga y exploración de los datos con pandas.
2. Balanceo de clases con RandomOverSampler (imbalanced-learn), que duplica registros de la clase minoritaria: cada clase pasa a 4.208 registros.
3. Codificación de las variables categóricas con One-Hot Encoding (scikit-learn), ya que no tienen un orden entre categorías.
4. Árbol de decisión con scikit-learn (criterio entropía, profundidad máxima 7, mínimo 2 muestras por hoja).
5. Evaluación con validación cruzada de 10 pliegues.
6. Visualización del árbol con Matplotlib (`plot_tree`).

## Resultados
Promedio de la validación cruzada de 10 pliegues:

| Métrica | Valor |
|---|---|
| Exactitud | 99,9 % |
| F1 ponderado | 0,999 |
| Precisión ponderada | 0,999 |
| Recall ponderado | 0,999 |

Nota: este dataset es conocido por ser muy separable con las características disponibles, por lo que un resultado cercano al 100 % es esperable.

## Árbol de decisión
<img width="2035" height="944" alt="arbol_decision_hongo" src="https://github.com/user-attachments/assets/74fb6977-e31e-47dd-9efe-e901c36e1f53" />

## Cómo ejecutarlo en Google Colab
1. Abre el notebook `Practica_ML_Hongos.ipynb` en Google Colab.
2. Ejecuta las celdas en orden. El dataset se descarga automáticamente desde OpenML, por lo que necesitas conexión a internet y no debes subir ningún archivo.
