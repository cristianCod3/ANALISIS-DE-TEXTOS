# ANALISIS-DE-TEXTOS
Motor de Procesamiento de Lenguaje Natural (PLN) desde cero en Python para clasificación de tópicos mediante álgebra lineal.
# Clasificador Inteligente de Tópicos (NLP desde cero)

[![Python Version](https://img.shields.io/badge/python-3.8%2B-blue.svg)](https://www.python.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Framework: Tkinter](https://img.shields.io/badge/UI-Tkinter%20%2F%20TTK-orange.svg)](https://docs.python.org/3/library/tkinter.html)

Una aplicación de escritorio nativa desarrollada en Python que implementa un motor de **Procesamiento de Lenguaje Natural (PLN)** completo desde sus fundamentos matemáticos y estadísticos, sin depender de librerías externas de Machine Learning (como Scikit-Learn o SciPy).

El sistema analiza de forma dinámica cualquier texto introducido por el usuario y determina en tiempo real el porcentaje de afinidad con cuatro tópicos principales: **Programación, Coches, Ajedrez y Música**.

---

## Características y Fundamentos Matemáticos

El núcleo del proyecto radica en la implementación del pipeline de PLN clásico utilizando únicamente álgebra lineal y estructuras de datos nativas de Python:

1. **Preprocesamiento de Texto (Pipeline de Limpieza):**
   * Normalización completa (conversión a minúsculas y eliminación de caracteres especiales/puntuación).
   * Filtrado inteligente de *Stop Words* (palabras vacías en español).
   * Reducción léxica mediante *Stemming* (extracción de raíces de las palabras).

2. **Modelado Vectorial (TF-IDF):**
   * Construcción de un vocabulario global dinámico generado a partir de 12 textos semilla predefinidos (3 por cada categoría).
   * Cálculo de la **Frecuencia de Término ($TF$)**: Importancia local de una palabra en un documento.
   * Cálculo de la **Frecuencia Inversa de Documento ($IDF$)**: Importancia global de la palabra en todo el corpus mediante la fórmula:
     $$\text{IDF}(t) = \log\left(\frac{N}{|\{d \in D : t \in d\}|}\right)$$

3. **Métrica de Similitud Coseno:**
   * Comparación geométrica en un espacio vectorial multidimensional entre el vector generado por el texto del usuario ($A$) y los vectores promedio de cada tópico semilla ($B$):
     $$\text{Similitud}(A, B) = \frac{A \cdot B}{\|A\| \|B\|} = \frac{\sum_{i=1}^{n} A_i B_i}{\sqrt{\sum_{i=1}^{n} A_i^2} \sqrt{\sum_{i=1}^{n} B_i^2}}$$

4. **Interfaz Gráfica de Usuario (GUI):**
   * Diseñada con `Tkinter` y `ttk` usando componentes asíncronos simulados para representar los resultados mediante barras de progreso interactivas con cálculo exacto de porcentajes en tiempo real.

---

##  Tecnologías Utilizadas

* **Lógica y Frontend:** [Python 3](https://www.python.org/)
* **Interfaz Gráfica:** `Tkinter` / `ttk` (Módulos integrados en la librería estándar de Python)
* **Cálculos Matemáticos:** `math` (Librería estándar para funciones logarítmicas y raíces cuadradas)
* **Procesamiento de Lenguaje:** [NLTK](https://www.nltk.org/) (Únicamente la clase `SnowballStemmer` optimizada para el idioma español)

---

## Instalación y Requisitos

Sigue estos pasos para clonar el repositorio y ejecutar el proyecto en tu máquina local:

### 1. Clonar el repositorio
Abre tu terminal y clona este proyecto usando Git:
```bash
git clone [https://github.com/tcristianCod3/ANALISIS-DE-TEXTOS.git](https://github.com/cristianCod3/ANALISIS-DE-TEXTOS.git)
cd ANALISIS-DE-TEXTOS


instala los archivos necesario mediante:

pip install nltk
