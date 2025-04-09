# Proyecto: Análisis Exploratorio y Preprocesamiento del Dataset Heart Cleveland (UCI)

## Descripción

Este proyecto realiza un Análisis Exploratorio de Datos (EDA) y el preprocesamiento necesario sobre el dataset "Heart Cleveland" de la UCI. El objetivo es comprender las características de los datos, identificar patrones, visualizar distribuciones y preparar el conjunto de datos para un posible modelado predictivo de enfermedades cardíacas.

Se utiliza Python con las bibliotecas estándar de análisis de datos (Pandas, NumPy, Matplotlib, Seaborn). Los resultados clave y visualizaciones (tablas HTML, box plots, histogramas, mapas de calor) se generan a través de scripts o notebooks de Jupyter.

**Nota Importante:** Varias columnas contienen valores numéricos (0, 1, 2, 3...) que representan **categorías** específicas, no necesariamente valores binarios o continuos directos (ver Diccionario de Datos).

## Variable Objetivo

El objetivo principal suele ser predecir la columna `condition`:

* **`condition`**: Diagnóstico de enfermedad cardíaca.
    * `0`: Ausencia de enfermedad cardíaca (Negativo).
    * `1`: Presencia de enfermedad cardíaca (Positivo).

## Diccionario de Datos (Columnas)

Descripción detallada de cada columna en el dataset:

* **`age`**: Edad del paciente (años).
    * *Rango observado en este dataset: 29 - 77 años.*
* **`sex`**: Sexo del paciente.
    * `1`: Masculino
    * `0`: Femenino
* **`cp`**: Tipo de dolor de pecho experimentado.
    * `0`: Angina típica
    * `1`: Angina atípica
    * `2`: Dolor no anginoso
    * `3`: Asintomático
* **`trestbps`**: Presión arterial en reposo (en mm Hg).
* **`chol`**: Colesterol sérico (en mg/dl).
* **`fbs`**: Nivel de azúcar en sangre en ayunas > 120 mg/dl.
    * `1`: Verdadero
    * `0`: Falso
* **`restecg`**: Resultados electrocardiográficos en reposo.
    * `0`: Normal
    * `1`: Anormalidad de la onda ST-T
    * `2`: Hipertrofia ventricular izquierda probable (Estes)
* **`thalach`**: Frecuencia cardíaca máxima alcanzada durante prueba de esfuerzo.
* **`exang`**: Angina inducida por el ejercicio.
    * `1`: Sí
    * `0`: No
* **`oldpeak`**: Depresión del segmento ST inducida por el ejercicio en relación con el reposo (valor numérico).
* **`slope`**: Pendiente del segmento ST máximo durante el ejercicio.
    * `0`: Pendiente ascendente
    * `1`: Plano
    * `2`: Pendiente descendente
* **`ca`**: Número de vasos principales (0-3) coloreados por fluoroscopia.
* **`thal`**: Resultado de la prueba de esfuerzo con Talio.
    * `0`: Normal
    * `1`: Defecto fijo
    * `2`: Defecto reversible
* **`condition`**: Presencia (1) o ausencia (0) de enfermedad cardíaca (Variable Objetivo).

## Preprocesamiento Realizado / Considerado

Durante el análisis, se aplicaron o consideraron los siguientes pasos de preprocesamiento:

1.  **Valores Faltantes:** Se verificó la ausencia de valores nulos en el dataset. (Resultado: No se encontraron nulos).
2.  **Duplicados:** Se revisó y eliminó cualquier fila duplicada para asegurar la unicidad de los registros.
3.  **Valores Atípicos (Outliers):** Se identificaron visualmente (box plots) y numéricamente (IQR) outliers en variables como `trestbps`, `chol`, `thalach`, `oldpeak`. Su tratamiento (ej. acotación, transformación o mantenerlos) dependerá de los requisitos del análisis o modelo posterior.
4.  **Codificación Categórica:** Se identificaron las variables categóricas (incluso las numéricas como `cp`, `thal`, etc.) y se demostró el uso de One-Hot Encoding (`pd.get_dummies`) para convertirlas a un formato adecuado para la mayoría de modelos de Machine Learning.
5.  **Escalado de Características:** Se mencionó la importancia de escalar variables numéricas (ej. usando `StandardScaler` o `MinMaxScaler` de Scikit-learn) antes de entrenar ciertos tipos de modelos, aunque no se aplicó directamente en la fase de EDA para mantener la interpretabilidad.

## Instalación

Para ejecutar el análisis localmente, necesitas Python 3.x y las siguientes bibliotecas principales. Se recomienda usar un entorno virtual.

1.  **Clona el repositorio (si aplica):**
    ```bash
    git clone [URL-DEL-REPOSITORIO]
    cd [NOMBRE-DEL-DIRECTORIO]
    ```
2.  **Crea e instala las dependencias:**
    Se recomienda usar el archivo `requirements.txt` (si se proporciona uno).
    ```bash
    # Opcional: Crea un entorno virtual
    # python -m venv venv
    # source venv/bin/activate  # En Linux/macOS
    # .\venv\Scripts\activate  # En Windows

    # Instala las bibliotecas
    pip install -r requirements.txt
    ```
    Si no hay `requirements.txt`, puedes instalar las bibliotecas clave manualmente:
    ```bash
    pip install pandas numpy matplotlib seaborn jupyterlab # O jupyter notebook
    ```
    *(Nota: `os`, `webbrowser`, `math` son parte de la biblioteca estándar de Python)*

## Uso

1.  Asegúrate de tener el archivo de datos `heart_cleveland_upload.csv` en la ubicación correcta (ej. misma carpeta o ruta especificada en el código).
2.  Inicia Jupyter Lab o Jupyter Notebook desde tu terminal en el directorio del proyecto:
    ```bash
    jupyter lab
    # o
    jupyter notebook
    ```
3.  Abre el archivo principal del notebook (ej. `analisis_heart_cleveland.ipynb`).
4.  Ejecuta las celdas del notebook en orden para reproducir el análisis, las visualizaciones y el preprocesamiento. Los archivos HTML generados (estadísticas, tablas) se guardarán en el mismo directorio.

## Contribución

Actualmente, no se buscan contribuciones externas activamente, pero si encuentras errores o tienes sugerencias, puedes abrir un "Issue" en el repositorio (si aplica).

## Licencia

Este proyecto se distribuye bajo la Licencia MIT. Consulta el archivo `LICENSE` para más detalles (si existe), o considera que el código es para fines educativos/demostrativos si no se especifica una licencia formal.