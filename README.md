Predicción de Enfermedades Cardíacas - Analítica Predictiva
Este repositorio contiene la implementación de un modelo de Machine Learning para predecir si un paciente tiene enfermedad cardíaca.

Descripción del Proyecto
Este repositorio contiene la implementación completa de un modelo de Machine Learning para predecir si un paciente tiene enfermedad cardíaca. El modelo fue desarrollado desde cero utilizando Regresión Logística, sin depender de librerías de Machine Learning para el entrenamiento.

El Problema
Las enfermedades cardíacas son la principal causa de muerte en el mundo. La Organización Mundial de la Salud reporta más de 17 millones de fallecimientos anuales por esta causa. La detección temprana es crucial para salvar vidas, pero muchos pacientes no presentan síntomas hasta que la enfermedad está avanzada.

Este proyecto busca responder: Dados los datos clínicos de un paciente, ¿tiene enfermedad cardíaca o no? La respuesta es binaria: Sí o No.

Metodología
Se ha seleccionado la Regresión Logística como método de clasificación. Este algoritmo procesa variables de entrada continuas y categóricas, generando una salida discreta probabilística (enfermo o sano). Las razones de esta elección son:

Probabilístico: No solo dice "sí" o "no", sino que asigna una probabilidad como 85% de riesgo.

Interpretable: Podemos ver qué factores influyen más en la enfermedad.

Eficiente: Funciona muy bien con datasets de tamaño moderado como el utilizado.

Variables del Modelo
Continuas (Inputs): Edad, Presión arterial, Colesterol, Frecuencia cardíaca máxima, Depresión del segmento ST.

Categóricas (Inputs): Sexo, Tipo de dolor de pecho, Número de vasos afectados, Resultados de talio.

Discreta (Salida): Enfermedad cardíaca (0 = Sano, 1 = Enfermo).

El Dataset
El dataset utilizado proviene del UCI Heart Disease Repository. Contiene información de 270 pacientes con 13 características clínicas. La distribución es:

150 pacientes están sanos (Absence)

120 pacientes tienen enfermedad (Presence)

El dataset está balanceado, lo que permite que el modelo aprenda sin sesgos hacia ninguna clase.

Sustento Matemático
Función Sigmoide: Convierte cualquier número real en una probabilidad entre 0 y 1.

Fórmula: σ(z) = 1 / (1 + e^(-z))

Si z es muy grande positivo, σ(z) se acerca a 1 que significa enfermo. Si z es muy negativo, σ(z) se acerca a 0 que significa sano.

Combinación Lineal: Antes de aplicar la sigmoide, se calcula z como una suma ponderada de las características.

Fórmula: z = β₀ + β₁·Edad + β₂·Colesterol + ... + βₙ·Sexo

Función de Costo (Cross-Entropy): Mide qué tan mal está prediciendo el modelo.

Fórmula: J = -[y·log(p) + (1-y)·log(1-p)]

Si el modelo acierta, el costo es bajo. Si falla, el costo es alto.

Descenso de Gradiente: Algoritmo que minimiza el costo ajustando los coeficientes β.

Fórmula: β_nuevo = β_viejo - α · ∇J

Donde α es la tasa de aprendizaje y ∇J es el gradiente (dirección de ajuste).

Resultados Obtenidos
Precisión (Accuracy): 83.33% - El modelo acierta en 5 de cada 6 pacientes.

Sensibilidad (Recall): 76.2% - El modelo detecta a 3 de cada 4 pacientes enfermos.

Especificidad: 87.9% - El modelo identifica correctamente a 9 de cada 10 pacientes sanos.

AUC-ROC: 0.928 - Considerado excepcional. Esto significa que el modelo separa correctamente a enfermos de sanos en el 92.8% de los casos.

Factores Más Importantes
Según los coeficientes aprendidos por el modelo, los mejores predictores de enfermedad cardíaca son:

Tipo de dolor de pecho - El predictor más fuerte

Sexo - Ser hombre aumenta el riesgo

Número de vasos afectados - A más vasos, más riesgo

Depresión del segmento ST - Medida eléctrica anormal del corazón

Frecuencia cardíaca máxima - A mayor frecuencia, menor riesgo (factor protector)

Requisitos e Instalación
El sistema requiere Python 3.7 o superior.

Paso 1: Clonar este repositorio

Paso 2: Instalar las dependencias necesarias:

pip install numpy pandas matplotlib seaborn scikit-learn

Paso 3: Ejecutar el notebook en Google Colab o Jupyter:

jupyter notebook heart_disease_project.ipynb

Estructura del Código
El código está organizado de manera modular en las siguientes secciones:

cargar_datos: Lectura del dataset CSV y visualización inicial.

preprocesar_datos: Limpieza y conversión de variables categóricas a numéricas.

analizar_correlaciones: Cálculo de correlaciones de Pearson y prueba Chi-cuadrado.

entrenar_modelo: Implementación manual de Regresión Logística con descenso de gradiente.

animacion_aprendizaje: Visualización en tiempo real de cómo disminuye el error.

evaluar_modelo: Cálculo de matriz de confusión, precisión y curva ROC.

visualizar_resultados: Generación de gráficas profesionales.

comparar_sklearn: Validación comparando con scikit-learn.

Visualizaciones Incluidas
El proyecto genera las siguientes gráficas:

Gráfica de barras con la distribución de pacientes (sanos vs enfermos)

Mapa de calor de correlaciones (matriz de correlación)

Animación de la evolución del costo durante el entrenamiento

Gráfica de barras horizontales con los 5 features más importantes

Matriz de confusión en formato heatmap

Curva ROC con el valor de AUC

Boxplot comparando edades entre sanos y enfermos

Video de Sustentación
Enlace al video de 5 minutos - Pendiente de subir

Conclusiones
La Regresión Logística implementada desde cero alcanzó una precisión del 83.33%.

El AUC de 0.928 califica al modelo como excepcional para uso médico.

Las variables más importantes son el tipo de dolor de pecho y el número de vasos afectados.

El modelo fue validado correctamente comparándolo con la implementación de scikit-learn.

Este proyecto demuestra que se puede implementar Machine Learning desde cero entendiendo cada paso matemático.

Primero, asegúrate de tener Python instalado. Luego instala las librerías necesarias:


### Matriz de Confu
