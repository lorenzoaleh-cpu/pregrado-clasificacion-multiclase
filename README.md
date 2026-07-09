# pregrado-clasificacion-multiclase

## Evaluación y Extensión Multiclase de Modelos PSVM y CPSVM

Este repositorio contiene el código fuente, los conjuntos de datos y la experimentación utilizados para el trabajo de pregrado titulado **"[Escribe aquí el título oficial de tu memoria/tesis]"**, desarrollado por **Lorenzo Aleh** ([Mes] 202X).

---

### Descripción del Proyecto

El objetivo de este trabajo es estudiar, corregir y extender empíricamente los modelos Probabilistic Support Vector Machine (PSVM) y Conditional Probabilistic Support Vector Machine (CPSVM) al contexto de clasificación multiclase, comparando su desempeño frente al SVM clásico mediante las estrategias *One-versus-All* (OvA), *One-versus-One* (OvO) y *All-Together*.

El repositorio se divide en tres bloques prácticos correspondientes a los capítulos de la memoria:

1. **Capítulo 3 - Marco Teórico e Ilustraciones**: Implementaciones propias en el espacio bidimensional para ilustrar geométricamente los modelos SVM, PSVM y CPSVM, incluyendo sus formulaciones primal y dual corregidas, el truco del kernel (RBF) y las estrategias multiclase OvA, OvO y All-Together.
2. **Capítulo 4 - Visualizaciones Metodológicas**: Scripts desarrollados para generar ejemplos visuales que facilitan la comprensión de la metodología aplicada en la tesis. Incluye representaciones gráficas de la matriz de confusión y esquemas visuales del proceso de partición en la validación cruzada (*k-folds*), siendo códigos puramente ilustrativos.
3. **Capítulo 5 - Experimentación, Metodología y Análisis Estadístico**: Núcleo experimental del trabajo. Consiste en la resolución de los problemas de optimización cuadrática convexa mediante los *solvers* CVXPY y `quadprog` en Python, con selección de hiperparámetros a través de validación cruzada de 10 pliegues. Contiene la evaluación comparativa de 7 modelos (MC-SVM, OvA-SVM, OvO-SVM, OvA-PSVM, OvO-PSVM, OvA-CPSVM y OvO-CPSVM) bajo kernel lineal y RBF sobre 9 conjuntos de datos estándar de UCI, utilizando las métricas BACCU y ACCU. Finaliza con un análisis estadístico no paramétrico basado en rankings mediante las pruebas de Friedman con corrección de Iman-Davenport y *post-hoc* de Nemenyi.

---

### Estructura del Repositorio

La arquitectura del proyecto está organizada de la siguiente manera:

* `Capitulo_3/`: Scripts creados para explicar la formulación matemática y generar las fronteras de decisión teóricas bidimensionales.
    * Implementación algorítmica y resolución cuadrática usando los *solvers* CVXPY y `quadprog`.
* `Capitulo_4/`: Códigos de apoyo visual enfocados en explicar las metodologías de evaluación (matrices de confusión y esquemas *k-fold* de ejemplo).
* `Capitulo_5/`: Flujo experimental principal de la tesis.
    * Experimentación multiclase sobre los conjuntos de datos, validación cruzada y generación de métricas (BACCU y ACCU).
    * Ejecución de las pruebas estadísticas no paramétricas y exportación de resultados.
* `datasets/`: 9 conjuntos de datos estándar obtenidos del repositorio UCI Machine Learning, preprocesados para los experimentos.

---

### Requisitos y Ejecución

* **Software**: Entorno de ejecución basado en Python 3.3 o superior.
* **Dependencias principales**: Es estrictamente necesario tener instaladas las librerías de optimización matemática y análisis de datos. Se pueden instalar mediante:
    ```bash
    pip install cvxpy numpy scipy scikit-learn pandas matplotlib
    ```
* **Instrucciones de Ejecución**:
    1. Clonar este repositorio en tu entorno local.
    2. Para reproducir las figuras teóricas e ilustraciones geométricas, ejecutar los *notebooks* o scripts ubicados en la carpeta `Capitulo_3/`.
    3. Para visualizar los ejemplos metodológicos, revisar los archivos en `Capitulo_4/`.
    4. Para ejecutar la experimentación completa (resolución de modelos y análisis estadístico), correr los scripts maestros ubicados dentro de `Capitulo_5/`.

---

### Autoría y Agradecimientos

**Trabajo del autor**: La extensión matemática de los modelos al entorno multiclase, la corrección de las formulaciones primal y dual, la arquitectura del flujo experimental, el sistema de validación cruzada y la implementación del análisis estadístico han sido desarrollados íntegramente por el autor de este trabajo.

**Código proporcionado y herramientas**: Se agradece el uso de las librerías de código abierto de Python (como CVXPY y `quadprog`), que sirvieron como motor computacional fundamental para la resolución de los problemas de optimización cuadrática convexa documentados en la memoria, garantizando la total reproducibilidad de los experimentos.
