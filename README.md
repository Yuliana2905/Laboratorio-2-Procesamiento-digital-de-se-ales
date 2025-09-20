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


y[n] = { 5, 6, 35, 72, 54, 37, 90, 105, 88, 93, 54, 26, 58, 48, 15, 0 }

<img width="936" height="336" alt="image" src="https://github.com/user-attachments/assets/a2854722-c581-4b06-9f88-45174fd418a3" />

y[n] = { 5, 6, 35, 72, 54, 37, 90, 105, 88, 93, 54, 26, 58, 48, 15, 0 }

y[n]=x[n]∗h[n]
Se realiza la sumatoria para cada valor de 
𝑛
n, obteniendo la secuencia completa de 
𝑦[𝑛] y [n].

#### 3-Representación manual de resultados:
Grafica de las señal X[𝑛] 
### Yuliana 
<img width="1194" height="1600" alt="image" src="https://github.com/user-attachments/assets/a617f38f-88de-4767-af41-18a97d487aa7" />

Grafica la señal de salida  𝑦[𝑛]
### Yuliana 
<img width="1558" height="1600" alt="image" src="https://github.com/user-attachments/assets/a5d4b331-bb86-448b-8e72-0e053cd56599" />

### Yuliana 
y[n] en función de 𝑛
<img width="1299" height="1600" alt="image" src="https://github.com/user-attachments/assets/012a8c94-2bab-4817-b7d8-4d1637a43816" />


### Camila
y[n] en función de 𝑛

![Imagen de WhatsApp 2025-09-02 a las 20 56 49_7b87bdb6](https://github.com/user-attachments/assets/dd8eaa84-1a1f-4b31-a9ee-2562ea5216a9)

### Camila
Grafica de las señal X[𝑛] 
![Imagen de WhatsApp 2025-09-18 a las 16 46 06_9ddfaf9e](https://github.com/user-attachments/assets/caa132e2-ec3f-40b2-af46-aecb4f233573)

### Camila
Grafica la señal de salida  𝑦[𝑛]
![Imagen de WhatsApp 2025-09-18 a las 16 46 06_5c03650c](https://github.com/user-attachments/assets/a86c2d9f-169b-4641-852d-155cc2172b9b)

## Adriana
y[n] en función de n 

<img width="1257" height="800" alt="image" src="https://github.com/user-attachments/assets/70a01cfb-e0cf-445b-afed-429203dff5ff" />

Grafica de la señal h(n) codigo estudiante 

<img width="566" height="799" alt="image" src="https://github.com/user-attachments/assets/7532b672-e133-4d13-957c-04e3dcc27959" />

Grafica de la señal x(n) documento identidad

<img width="1074" height="823" alt="image" src="https://github.com/user-attachments/assets/5736a26d-000a-479e-856b-60c2b3a4f4d5" />




#### 3-Representación por medio de Phyton de resultados:
## Grafica h(n)
Se definió la señal discreta h(n) y se representó mediante la función plt.stem, que permite graficar valores discretos en forma de impulsos. En la gráfica se observa la variación de la amplitud de la señal en función del índice n, añadiendo título y etiquetas a los ejes para una mejor interpretación.
```python
x = [0, 1, 2, 3, 4, 5, 6]
h = [5, 6, 0, 0, 8, 5, 0]

plt.stem(x,h)
plt.title('Grafica señal h(n)', fontsize=14, fontweight='bold')
plt.xlabel('Índice discreto n', fontsize=12)
plt.ylabel('Amplitud de h[n]', fontsize=12)
Se grafica la señal de salida  𝑦[𝑛]
```

## Yuliana


<img width="599" height="447" alt="image" src="https://github.com/user-attachments/assets/9101fcf3-5888-4567-9f20-44264a940b3c" />

## Camila

<img width="618" height="456" alt="image" src="https://github.com/user-attachments/assets/a94928b5-2ce9-48f4-9076-024886c9d502" />


## Adriana

<img width="593" height="443" alt="image" src="https://github.com/user-attachments/assets/5be7e866-7242-4667-b8e1-b6359e0d32a2" />

## Grafica x(n)
Se definió la señal discreta x(n) y se representó con la función plt.stem, que grafica los valores como impulsos verticales. La gráfica muestra la amplitud de la señal en función del índice n, con título y etiquetas en los ejes para facilitar su interpretación.
```python
x = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
h = [1, 0, 7, 6, 2, 4, 2, 2, 6, 3]

plt.stem(x,h)
plt.title('Grafica señal x(n)', fontsize=14, fontweight='bold')
plt.xlabel('Índice discreto n', fontsize=12)
plt.ylabel('Amplitud de x[n]', fontsize=12)
```


## Yuliana

<img width="598" height="447" alt="image" src="https://github.com/user-attachments/assets/a613ac1f-4d31-4426-8c73-370e39e4e5b1" />


## Camila

<img width="579" height="454" alt="image" src="https://github.com/user-attachments/assets/f9eddb5c-0ae5-49cb-b6ab-814b3e861377" />


## Adriana

<img width="562" height="454" alt="image" src="https://github.com/user-attachments/assets/3f0a023e-0ef1-49b1-b68b-81a031122b0b" />


### Convolucion:

Para ello se utiliza la función np.convolve(x, h), la cual genera una nueva secuencia y[n] que representa el resultado de combinar ambas señales.

Posteriormente, con matplotlib, se grafica el resultado en un diagrama de tallo (stem plot), el cual es adecuado para señales discretas.

```python
import numpy as np
import matplotlib.pyplot as plt

x = np.array([1,0,7,3,5,9,9,5,7,0])
h = np.array([5,6,0,0,8,6,2])
y=np.convolve(x,h)
plt.figure(figsize=(10,4))
plt.stem(y)
plt.title('Convolución de las señales x[n] y h[n]', fontsize=14, fontweight='bold')
plt.xlabel('Índice discreto n', fontsize=12)
plt.ylabel('Amplitud de y[n]', fontsize=12)
plt.grid(True)
plt.show()
```


## Convolucion Yuliana
<img width="1144" height="515" alt="image" src="https://github.com/user-attachments/assets/7ddbdfa1-9630-4e7b-89d1-f2f9f832f101" />


## Convolucion Camila
<img width="881" height="400" alt="image" src="https://github.com/user-attachments/assets/a7768153-391f-479d-a810-33e514b624da" />


## Convolucion Adriana
<img width="864" height="390" alt="image" src="https://github.com/user-attachments/assets/7bb6f78a-c66e-48fc-afc5-8d6088c92cac" />


# PARTE B
Para la parte b se definieron las señales pedidas en el informe para Ts= 1.25ms.
1. encontrar la correlación cruzada entre ambas señales.
```python
Ts=1.25e-3
n=np.arange(0, 9)
t=n*Ts

x1=np.cos(2*np.pi*100*t)
x2=np.sin(2*np.pi*100*t)

corr=np.correlate(x1, x2, mode="full")
lags=np.arange(-len(x1)+1, len(x1))

plt.figure(figsize=(12, 6))
plt.subplot(3,1,1)
plt.stem(n,x1,basefmt="k")
plt.title("Señalx1[n]=cos(2π100nTs)")
plt.xlabel("n(muestras)")
plt.ylabel("x1[n]")
plt.subplot(3,1,2)
plt.stem(n,x2,basefmt="k")
plt.title("Señalx2[n]=sin(2π100nTs)")
plt.xlabel("n(muestras)")
plt.ylabel("x2[n]")
plt.subplot(3,1,3)
plt.stem(lags, corr, basefmt="k")
plt.title("Correlación cruzada entre x1[n] y x2[n]")
plt.xlabel("Desplazamiento (lags)")
plt.ylabel("Correlación")

plt.tight_layout()
plt.show()

print("x1 =", np.round(x1, 4))
print("x2 =", np.round(x2, 4))
print("Correlación cruzada =", np.round(corr, 4))
```   
<img width="760" height="364" alt="image" src="https://github.com/user-attachments/assets/b75485b1-4461-4a5e-92af-e9d370e53d6b" />
2. se encontro la representacion grafica que describia la secuencia resultante 

3. Las correlciones cruzadas son una herramienta muy util para medir la similitud entres dos señales segun su desplazamiento se aplica en situaciones practicas como estamiacion de retardo cuando una señal llega con un restraso a un sistema, la correlacion cruzada permite encontrar el desfase temporal.
deteccion y coincidencia de patrones en una señal larga como señales electrocardiograficos, localizacion y alineamientos para señales con multicanal o sincronizar grabaciones, medicion de 
medición de similitud del ruido atenuando el ruido no correlacionado por eso es util en deteccion de señales debiles en ambientes ruidosos 
# DIAGRAMAS DE FLUJO

### Diagrama de flujo parte A señal h(n):

<img width="337" height="674" alt="image" src="https://github.com/user-attachments/assets/ea863fd6-05c0-47c4-b393-b95f4abba0b3" />

### Diagrama de flujo parte A señal x(n):

<img width="305" height="714" alt="image" src="https://github.com/user-attachments/assets/7510bec6-0919-4d6d-8242-abbb597646cf" />



### Diagrama de flujo parte A convolucion:

<img width="345" height="754" alt="image" src="https://github.com/user-attachments/assets/eebffda4-38cd-4645-8674-0cd9d6daa861" />

### Diagrama de flujo parte B correlacion:

<img width="307" height="715" alt="image" src="https://github.com/user-attachments/assets/01b64000-fda7-48ad-82d1-76ae1e7207fc" />


### Diagrama de flujo parte C señales de flujo:










 
