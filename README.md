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

## Convolución:
Es una operación matemática que describe la salida de un sistema lineal e invariante en el tiempo (LTI) cuando se conoce su respuesta al impulso 

<img width="316" height="85" alt="image" src="https://github.com/user-attachments/assets/daeea36c-7652-43de-91f9-7bb9db13576d" />


La convolución permite analizar cómo un sistema modifica una señal, siendo fundamental en el diseño de filtros digitales.

## Correlación:
Es una medida de similitud entre dos señales. La correlación cruzada entre 
𝑥1[𝑛]x1[n] y 𝑥2[𝑛]x2
[n] se define como:
	​
<img width="378" height="99" alt="image" src="https://github.com/user-attachments/assets/65dcdc44-90fe-49ac-9d06-dde472760180" />

Cuando una señal se correlaciona consigo misma se obtiene la autocorrelación, útil para detectar periodicidad, redundancias y presencia de ruido. La correlación cruzada se emplea en sincronización de señales y detección de patrones en aplicaciones biomédicas y de telecomunicaciones.

## Transformada de Fourier (TF):
Permite representar una señal en el dominio de la frecuencia. Su versión discreta se conoce como Transformada Discreta de Fourier (DFT) y se implementa eficientemente mediante la Transformada Rápida de Fourier (FFT). Su definición es:

<img width="295" height="112" alt="image" src="https://github.com/user-attachments/assets/3dd3ed61-9112-468f-b997-b633f3853f8d" />

La FFT posibilita obtener el espectro de una señal, analizando su contenido en frecuencias. Este análisis es esencial para caracterizar señales biológicas, determinar su densidad espectral de potencia y estudiar parámetros como frecuencia media, mediana y desviación estándar.

En conjunto, estas herramientas permiten comprender tanto el comportamiento temporal como espectral de las señales, lo que resulta indispensable en aplicaciones de la ingeniería biomédica, el procesamiento de audio, las telecomunicaciones y el control de sistemas digitales.

# Objetivos: 
·Comprender la convolución como una operación que permite obtener la respuesta de un sistema discreto ante una entrada determinada. 
·Analizar la correlación como medida de similitud entre dos señales. 
·Aplicar la Transformada de Fourier como herramienta de análisis en el dominio de la frecuencia.

# Procedimiento y resultados: 
## PARTE A 
Teniendo el sistema h[n] = {cada dígito de su código} (ej: h[n] = {5,6,0,0,1,4,6}) y la 
señal x[n] = {cada dígito de su cédula} (ej: x[n]={1,0,2,1,4,5,4,8,1,9}): 
1. Encuentre la señal  𝑦[𝑛] resultante de la convolución usando sumatorias (a 
mano). 
2. Encuentre la representación gráfica y secuencial (a mano). 
3. Encuentre la señal 𝑦[𝑛] resultante de la convolución usando Python. 
4. Encuentre la representación gráfica y secuencial usando Python. 
## Procedimiento: 
Definición de señales:

#### 1- Se define la señal del sistema 
### Yuliana
ℎ[𝑛]=  {5,6,0,0,8,6,2}
### Adriana 
ℎ[𝑛]= {5,6,0,0,8,5,0}
### Camila
ℎ[𝑛]=  {5,6,0,0,8,5,5}
### Yuliana 
𝑥[𝑛]= {1,0,7,3,5,9,9,5,7,0}
### Adriana 
𝑥[𝑛]= {1,0,7,6,2,4,2,2,6,3}
### Camila
𝑥[𝑛]= {1,0,2,7,2,8,1,6,7,6}

#### 2- Cálculo manual de la convolución:

Se aplica la definición discreta de la convolución:
<img width="288" height="96" alt="image" src="https://github.com/user-attachments/assets/9536a32e-def4-4f1f-8c89-0330b21ccf58" />
### Yuliana 
Calculos manuales:

**<img width="916" height="835" alt="image" src="https://github.com/user-attachments/assets/13a401ca-f4b3-447f-90ee-5569e447330f" />
**

<img width="436" height="363" alt="image" src="https://github.com/user-attachments/assets/867c3bdf-4552-4d20-a786-4cd30dc24a56" />

y[n] = { 5, 6, 35, 57, 51, 81, 157, 145, 137, 150, 136, 112, 104, 52, 14, 0 }

y[n]=x[n]∗h[n]
Se realiza la sumatoria para cada valor de 
𝑛
n, obteniendo la secuencia completa de 
𝑦[𝑛] y [n].
### Camila 
Calculos manuales:

![Imagen de WhatsApp 2025-09-02 a las 18 40 01_9a5d8e14](https://github.com/user-attachments/assets/2a949c63-92a1-44f0-be52-5f0b1da0b0c9)

<img width="681" height="355" alt="image" src="https://github.com/user-attachments/assets/66a162ed-e4b8-4e37-85a8-c5abe7facf01" />

y[n] = { 5, 6, 10, 47, 60, 57, 74, 102, 132, 181, 94, 93, 91, 113, 65, 30 }

y[n]=x[n]∗h[n]
Se realiza la sumatoria para cada valor de 
𝑛
n, obteniendo la secuencia completa de 
𝑦[𝑛] y [n].


## Adriana
Calculos manuales:

<img width="797" height="804" alt="image" src="https://github.com/user-attachments/assets/90782ae7-610d-4d26-a673-59faee99e62a" />


y[n] = { 5, 6, 35, 57, 51, 81, 157, 145, 137, 150, 136, 112, 104, 52, 14, 0 }

y[n]=x[n]∗h[n]
Se realiza la sumatoria para cada valor de 
𝑛
n, obteniendo la secuencia completa de 
𝑦[𝑛] y [n].
**

<img width="436" height="363" alt="image" src="https://github.com/user-attachments/assets/867c3bdf-4552-4d20-a786-4cd30dc24a56" />

y[n] = { 5, 6, 35, 57, 51, 81, 157, 145, 137, 150, 136, 112, 104, 52, 14, 0 }

y[n]=x[n]∗h[n]
Se realiza la sumatoria para cada valor de 
𝑛
n, obteniendo la secuencia completa de 
𝑦[𝑛] y [n].
#### 3-Representación manual de resultados:
Se grafica la señal de salida  𝑦[𝑛]
### Yuliana 

### Camila
y[n] en función de 𝑛

![Imagen de WhatsApp 2025-09-02 a las 20 56 49_7b87bdb6](https://github.com/user-attachments/assets/dd8eaa84-1a1f-4b31-a9ee-2562ea5216a9)

