# Detección y clasificación de escoliosis tipo S o tipo C

Este repositorio contiene el desarrollo de un pipeline automatizado en Python para el análisis geométrico y morfológico de radiografías de columna vertebral, orientado al diagnóstico y caracterización de la escoliosis. El proyecto fue desarrollado en entornos de Jupyter Notebook (Google Colab).

El sistema consta de dos módulos principales:
1. **Clasificador Topológico (C vs. S):** Un árbol de decisión jerárquico de doble vía que categoriza las deformidades en curvas simples "C" o curvas dobles "S".
2. **Calculador de Métricas Simples (Ápice y Desviación):** Un submódulo que evalúa localmente la geometría de la deformidad mediante el cálculo matemático de desplazamientos horizontales fila a fila, localizando de forma exacta las coordenadas espaciales del ápex y cuantificando la desviación lateral máxima.
   
Adicionalmente, cuenta con un módulo clínico exploratorio basado en procesamiento morfológico y trigonometría vectorial para cuantificar la severidad de la curva espinal, apuntando a una segmentación vértebra por vértebra.

---

## Configuración del Dataset 

El pipeline fue desarrollado utilizando Google Colab conectado a Google Drive como almacenamiento en la nube. Dado que el dataset original proviene de Kaggle y fue estructurado manualmente en Drive, cualquier usuario que descargue este proyecto deberá descargar el dataset y modificar las rutas. 

1. **Descargar el Dataset:** Obtener el conjunto de datos oficial desde [Kaggle: Types of Scoliosis](https://www.kaggle.com/datasets/f23296/types-of-scoliosis).
2. **Subir a Google Drive:** Cargar las carpetas de imágenes a Drive.
3. **Modificar las Rutas en el Notebook:** Al abrir el archivo `.ipynb`, se deberán modificar las constantes de configuración de directorios ubicadas en las primeras celdas para que coincidan con la estructura de carpetas de su propio Drive:

```python
# Modificar estas rutas según la ubicación de su dataset descargado:
DATA_DIR = '/content/drive/MyDrive/Tu_Ruta_Aqui/dataset'
CARPETA_C = r'/content/drive/MyDrive/Tu_Ruta_Aqui/dataset/training_set/c'
CARPETA_S = r'/content/drive/MyDrive/Tu_Ruta_Aqui/dataset/training_set/s'
PATH_IMAGEN = r"/content/drive/MyDrive/Tu_Ruta_Aqui/dataset/training_set/c/c.1.png"
