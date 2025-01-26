# 🎶 Generación y Guardado de Espectrogramas de Audio

Este proyecto está diseñado para procesar archivos de audio en formato `.mp3`, generar sus espectrogramas de Mel y guardarlos en dos versiones: con y sin leyenda. La leyenda incluye una barra de color que indica la escala de dB y un título. Los espectrogramas generados son imágenes que muestran cómo cambia la energía del sonido a lo largo del tiempo y las frecuencias.

## 📦 Requisitos

- Python 3.x
- Las siguientes bibliotecas son requeridas:
    - librosa
    - matplotlib
    - numpy

## 🗂️ Estructura del Proyecto

- **`input_folder`**: Carpeta que contiene los archivos de audio `.mp3` que se procesarán.
- **`output_folder_with_legend`**: Carpeta donde se guardarán los espectrogramas con leyenda.
- **`output_folder_clean`**: Carpeta donde se guardarán los espectrogramas sin leyenda.

## 📝 Descripción del Código

### 1. **🎧 Cargar Archivos de Audio**

El código carga los archivos `.mp3` desde la carpeta de entrada usando la función `librosa.load()`. Esto convierte el archivo de audio en una señal (`y`) y una frecuencia de muestreo (`sr`).

### 2. **📊 Generar Espectrograma de Mel**

A continuación, se genera un **espectrograma de Mel** usando la función `librosa.feature.melspectrogram()`. Este espectrograma es una representación visual de las frecuencias del audio en una escala perceptual que simula la forma en que los humanos percibimos el sonido.

### 3. **🔉 Convertir a Decibelios**

El espectrograma de Mel se convierte a una escala de decibelios usando `librosa.power_to_db()`, lo que facilita la visualización y mejora la interpretación de las diferencias de intensidad en el sonido.

### 4. **💾 Generar y Guardar Espectrogramas**

El código genera dos versiones del espectrograma:

- **Con leyenda**: Incluye la barra de color que indica los valores de dB y un título que describe el espectrograma.
- **Sin leyenda**: La imagen no tiene ejes ni título, lo que la hace más limpia y minimalista. Estas serán la data que usemos para entrenar a nuestro modelo.

Ambos espectrogramas se guardan como imágenes PNG en las carpetas correspondientes.

### 5. **👀 Visualización**

El espectrograma también se muestra en pantalla en el entorno de ejecución para su revisión inmediata.

## 🚀 Uso

1. Coloca los archivos `.mp3` en la carpeta `../data/sounds/`.
2. Ejecuta el código. Los espectrogramas generados se guardarán en las carpetas `spectograms_legend/` y `spectograms_clean/` como imágenes PNG.
3. Los espectrogramas con leyenda tendrán un título y una barra de colores que indica los niveles de dB, mientras que los espectrogramas sin leyenda no incluirán estos elementos.

## 📜 Ejemplo de Uso

El código se encuentra en `/src/preprocessing.ipynb` y se incluye en formato `.ipypnb` para poder ejecutar desde un notebook de Jupyter.

Después de ejecutar el código, encontrarás los espectrogramas generados en las carpetas correspondientes.

