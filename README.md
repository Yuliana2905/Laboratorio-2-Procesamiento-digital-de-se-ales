# Laboratorio 2 procesamiento digital de señales
## Convolución, correlación y transformada de Fourier 
## Docente: Carolina Corredor Bedoya
## Integrantes:
## ·Liseth Yuliana Clavijo 
## ·Maria Camila Rodriguez
## ·Adriana Valentina Alarcon 
## Fecha: Septiembre 2025


# Introducción:
El procesamiento digital de señales (PDS) es una de las herramientas fundamentales en la ingeniería, ya que permite analizar, transformar y extraer información relevante de señales en diferentes dominios. Dentro de este campo, la convolución se utiliza para determinar la respuesta de un sistema discreto a una señal de entrada, siendo esencial para comprender el comportamiento de filtros y sistemas lineales invariantes en el tiempo. Por otro lado, la correlación constituye un método de comparación entre señales, ya que mide su grado de similitud y es ampliamente empleada en detección de patrones, sincronización y análisis de señales biomédicas. Finalmente, la Transformada de Fourier brinda la posibilidad de estudiar las señales en el dominio de la frecuencia, facilitando la identificación de sus componentes espectrales y su caracterización estadística.

Este laboratorio busca integrar estos tres conceptos aplicados a ejemplos prácticos. Para ello, se realiza el cálculo de convolución tanto manual como mediante Python, se analiza la correlación cruzada entre señales sinusoidales y se estudia una señal biológica a partir de su muestreo y representación espectral. De esta manera, se fortalece la comprensión teórica y práctica de las principales herramientas del procesamiento digital de señales, resaltando su relevancia en aplicaciones de la ingeniería biomédica y áreas afines.

# Marco teorico:
El procesamiento digital de señales (PDS) se centra en la representación, análisis y manipulación de señales mediante técnicas matemáticas implementadas en computadoras y sistemas digitales. Entre sus herramientas principales se encuentran la convolución, la correlación y la transformada de Fourier, que permiten comprender y caracterizar el comportamiento de señales y sistemas.

Convolución:
Es una operación matemática que describe la salida de un sistema lineal e invariante en el tiempo (LTI) cuando se conoce su respuesta al impulso 

<img width="316" height="85" alt="image" src="https://github.com/user-attachments/assets/daeea36c-7652-43de-91f9-7bb9db13576d" />


La convolución permite analizar cómo un sistema modifica una señal, siendo fundamental en el diseño de filtros digitales.

Correlación:
Es una medida de similitud entre dos señales. La correlación cruzada entre 
𝑥
1
[
𝑛
]
x
1
	​

[n] y 
𝑥
2
[
𝑛
]
x
2
	​

[n] se define como:

