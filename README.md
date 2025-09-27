# 🐝 Proyecto Integrador – Apilamiento de Panales  
### Fase: Preparación y Procesamiento de Datos

Este repositorio contiene el notebook de **preparación de datos** para el proyecto de visión por computador orientado a la inspección de **apilamiento de panales**.  

El objetivo es asegurar que las imágenes estén **limpias, balanceadas y listas** para entrenar modelos de clasificación o segmentación.

---
<img width="954" height="510" alt="image" src="https://github.com/user-attachments/assets/002f0242-ba0b-4e09-b5ae-e20bfd198dbb" />

<img width="947" height="525" alt="image" src="https://github.com/user-attachments/assets/9c078b6f-6c1a-48b3-8b5f-92de973fb314" />


## ✅ Contenido del notebook

### 🔹 Parte 1 – Preprocesamiento y Análisis
1. **Configuración del proyecto**  
   Definición de rutas, parámetros globales y banderas de uso (pHash, embeddings).  

2. **Librerías y utilidades**  
   Importación de dependencias (OpenCV, PIL, scikit-learn, imbalanced-learn, torchvision, etc.).  

3. **Escaneo de imágenes**  
   - Lectura segura de imágenes desde carpetas clasificadas (`OK / DEFECTO`).  
   - Extracción de métricas iniciales (ancho, alto, brillo, blur, hash perceptual).  

4. **EDA (Exploratory Data Analysis)**  
   - Conteos por clase (balance de dataset).  
   - Histogramas de dimensiones, brillo y blur.  
   - Detección de duplicados (pHash).  
   - Identificación de imágenes corruptas o outliers.  

5. **Pipeline de limpieza (clase `DataCleaner`)**  
   - Redimensionado de imágenes a tamaño estándar (224×224).  
   - Eliminación de duplicados y corruptas.  
   - Generación de un dataset limpio en carpeta `dataset_clean/`.  

6. **Feature Engineering**  
   - Histogramas de color.  
   - HOG (Histogram of Oriented Gradients).  
   - Opcional: embeddings de modelos preentrenados (ResNet18).  
   - Exportación a CSV en carpeta `features/`.  

---

### 🔹 Parte 2 – Balanceo y División
7. **Balanceo de datos (SMOTE opcional)**  
   Generación de muestras sintéticas en el espacio de características para equilibrar clases.  

8. **Data Augmentation**  
   Transformaciones en imágenes reales:  
   - Rotaciones aleatorias.  
   - Flips horizontales/verticales.  
   - Jitter de brillo y contraste.  
   - Adición de ruido leve.  

9. **Partición estratificada en train/val/test**  
   - División en 70% train, 15% validation, 15% test (ajustable).  
   - Estructura final en `dataset_split/train|val|test`.  

10. **Baseline opcional con RandomForest**  
    - Entrenamiento rápido con features tabulares (Color + HOG).  
    - Reporte de precisión, recall, F1-score y matriz de confusión.  

11. **Próximos pasos**  
    - Revisar criterios de limpieza y augmentations aplicados.  
    - Activar `USE_EMBEDDINGS = True` para representaciones más ricas.  
    - Entrenar un modelo CNN o transfer learning (ResNet, MobileNet).  
    - Validar con métricas industriales (recall en defectos, precisión global).  

---

## 📂 Resultados

<img width="974" height="548" alt="image" src="https://github.com/user-attachments/assets/8466d3ba-317b-40b0-ba00-21c6f2c91a90" />

<img width="672" height="604" alt="image" src="https://github.com/user-attachments/assets/e8fc786e-f8d8-4621-9249-119431186353" />


---

## ⚙️ Requisitos principales
- Python 3.8+  
- Librerías:  
  ```bash
  pip install opencv-python pillow scikit-learn imbalanced-learn torch torchvision matplotlib seaborn imagehash scikit-image

---

## ⚙️ Autores 
- Francisco Javier Estupiñan Andrade 
- David Alejandro Narvaez Mejia 
