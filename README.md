# Predicción de Enfermedades Cardíacas - Analítica Predictiva

Este repositorio contiene la implementación de un modelo de **Machine Learning** para predecir si un paciente tiene enfermedad cardíaca basado en sus características clínicas.

## Metodología

Se ha seleccionado la **Regresión Logística** para procesar variables de entrada continuas y categóricas, generando una salida discreta probabilística (enfermo o sano). Este método fue elegido porque devuelve probabilidades, es interpretable y funciona bien con datasets médicos.

## Variables del Modelo

- **Continuas (Inputs):** Edad, Presión arterial, Colesterol, Frecuencia cardíaca máxima, Depresión del segmento ST.
- **Categóricas (Inputs):** Sexo, Tipo de dolor de pecho, Número de vasos afectados, Resultado de talio.
- **Discreta (Salida):** Enfermedad cardíaca (0 = Sano, 1 = Enfermo).

## Dataset

El dataset contiene información de **270 pacientes** con **13 características clínicas**. La distribución es de 150 pacientes sanos y 120 pacientes con enfermedad cardíaca.

## Sustento Matemático

- **Sigmoide:** Convierte cualquier número en probabilidad entre 0 y 1. Fórmula: σ(z) = 1 / (1 + e^(-z))
- **Combinación Lineal:** z = β₀ + β₁·Edad + β₂·Colesterol + ... + βₙ·Sexo
- **Costo (Cross-Entropy):** Mide el error del modelo. Fórmula: J = -[y·log(p) + (1-y)·log(1-p)]
- **Descenso de Gradiente:** Algoritmo que minimiza el costo. Fórmula: β_nuevo = β_viejo - α · ∇J

## Resultados Obtenidos

- **Precisión:** 83.33% (acierta 5 de cada 6 pacientes)
- **Sensibilidad:** 76.2% (detecta 3 de cada 4 enfermos)
- **Especificidad:** 87.9% (identifica 9 de cada 10 sanos)
- **AUC-ROC:** 0.928 (considerado excepcional)

## Factores Más Importantes

1. Tipo de dolor de pecho
2. Sexo (ser hombre aumenta el riesgo)
3. Número de vasos afectados
4. Depresión del segmento ST
5. Frecuencia cardíaca máxima (factor protector)

## Requisitos e Instalación

El sistema requiere **Python 3.7 o superior**.

1. Clone este repositorio.
2. Instale las dependencias necesarias:
