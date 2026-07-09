# pregrado-clasificacion-multiclase
Repositorio oficial con el código, datasets y experimentación para la extensión multiclase de modelos PSVM y CPSVM.

El objetivo de este trabajo es estudiar, corregir y extender empíricamente los modelos 
Probabilistic Support Vector Machine (PSVM) y Conditional Probabilistic Support Vector 
Machine (CPSVM) al contexto de clasificación multiclase, comparando su desempeño frente 
al SVM clásico mediante las estrategias One-versus-All (OvA), One-versus-One (OvO) y 
All-Together.

El repositorio se divide en tres bloques prácticos correspondientes a los capítulos de la memoria:

1. **Capítulo 3 - Marco Teórico e Ilustraciones**: Implementaciones propias en el espacio 
bidimensional para ilustrar geométricamente los modelos SVM, PSVM y CPSVM, incluyendo 
sus formulaciones primal y dual corregidas, el truco del kernel (RBF) y las estrategias 
multiclase OvA, OvO y All-Together.

2. **Capítulo 4 - Implementación y Metodología**: Resolución de los problemas de optimización 
cuadrática convexa mediante los solvers CVXPY y quadprog en Python, con selección de 
hiperparámetros óptimos a través de validación cruzada de 10 pliegues, evaluando los modelos 
con las métricas BACCU y ACCU sobre 9 conjuntos de datos estándar del repositorio UCI.

3. **Capítulo 5 - Experimentación y Análisis Estadístico**: Evaluación comparativa de los 7 
modelos (MC-SVM, OvA-SVM, OvO-SVM, OvA-PSVM, OvO-PSVM, OvA-CPSVM y OvO-CPSVM) 
bajo kernel lineal y RBF, con análisis estadístico no paramétrico basado en rankings mediante 
las pruebas de Friedman con corrección de Iman-Davenport y post-hoc de Nemenyi.
