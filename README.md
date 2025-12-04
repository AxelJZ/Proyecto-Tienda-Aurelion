# PROYECTO-TIENDA-AURELION

## 1. Descripción
Este repositorio contiene el proyecto organizado del análisis de datos "Tienda Aurelion".

## 2. Objetivos del Proyecto
Los objetivos principales de este trabajo son los siguientes:

- Integrar y preparar diversas fuentes de datos para su análisis.  
- Realizar un análisis exploratorio y estadístico inicial.  
- Identificar patrones relevantes en el comportamiento de los clientes y las ventas.  
- Desarrollar y evaluar un modelo predictivo sencillo, acorde al nivel introductorio del curso.  
- Elaborar conclusiones basadas en evidencia que puedan aportar valor analítico.

## 3. Conjuntos de Datos Utilizados
Los datos empleados en este proyecto corresponden a archivos de tipo Excel y CSV provistos para la actividad académica. Su estructura es la siguiente:

- **productos.xlsx:** Catálogo de productos disponibles.  
- **clientes.xlsx:** Información general de los clientes.  
- **ventas.xlsx:** Registro principal de transacciones realizadas.  
- **detalle_ventas.xlsx:** Desglose detallado de cada transacción.  
- **tabla_unificada.csv:** Archivo resultante del proceso de unificación y limpieza de datos.

## 4. Metodología
El desarrollo del proyecto siguió un enfoque secuencial, compuesto por las siguientes etapas:

1. **Carga y validación de los datos:** Revisión de estructura, duplicados, tipos de datos y consistencia general.  
2. **Limpieza y transformación:** Unificación de tablas, tratamiento de valores faltantes y estandarización de variables.  
3. **Análisis exploratorio y estadístico:** Obtención de métricas descriptivas, visualización de distribuciones y relaciones clave.  
4. **Modelo predictivo:** Entrenamiento de un modelo básico seleccionado según los criterios del curso; evaluación mediante métricas elementales.  
5. **Conclusiones:** Interpretación de los hallazgos más relevantes y del desempeño del modelo.

## 5. Estructura de carpetas

```
PROYECTO-TIENDA-AURELION/
├── README.md
├── notebooks/
│   ├── Analisis_Completo.ipynb
│   └── Conclusiones-Hallazgos_MdP.md
├── data/
│   ├── productos.xlsx
│   ├── clientes.xlsx
│   ├── ventas.xlsx
│   ├── detalle_ventas.xlsx
│   └── tabla_unificada.csv
├── src/
│   └── Programa.py
└── assets/
    └── Diagrama_Flujo.png
```

## 6. Cómo ejecutar el programa principal (PowerShell)

Abrir PowerShell en la carpeta del proyecto (`PROYECTO-TIENDA-AURELION`) y ejecutar:

```powershell
cd 'c:\(ruta)\PROYECTO-TIENDA-AURELION'
python .\src\Programa.py
```

- Seleccionar la opción `6` para cargar la `tabla_unificada.csv` y ejecutar la documentación (el notebook unificado se ejecutará si está instalado `jupyter`).
- La opción `1` abrirá el `README.md` del proyecto.

## 7. Dependencias

Instalación rápida (pip):

```powershell
pip install pandas numpy matplotlib seaborn scipy openpyxl jupyter ipython
```

Para garantizar la reproducibilidad, se recomienda instalar las dependencias antes de ejecutar el código.

## 8. Modelo Predictivo (Machine Learning)

Para complementar el análisis exploratorio realizado previamente, se desarrolló un modelo predictivo cuyo objetivo fue estimar el importe total de una venta a partir de variables del producto, cliente y transacción.

### 8.1. Objetivo del modelo

Predecir el valor de importe utilizando características numéricas y categóricas disponibles en el dataset unificado.

### 8.2. Variables utilizadas

- Variable objetivo (y):

    - importe — monto total de cada venta.

- Variables predictoras (X):

    - cantidad

    - precio_unitario

    - precio_unitario_producto

    - categoria_corregida

    - medio_pago

    - ciudad

    - nombre_producto

Tras filtrar registros sin importe válido, el dataset final quedó con 338 filas.

### 8.3. Preprocesamiento

- Eliminación de filas con importe nulo.

- Separación entre columnas numéricas y categóricas.

- Codificación de variables categóricas mediante OneHotEncoder (handle_unknown='ignore').

- Ensamble del procesamiento en un ColumnTransformer.

- División Train/Test (80% / 20%) con random_state=42.

### 8.4. Modelo seleccionado

Se utilizó RandomForestRegressor, dada su robustez para datos tabulares:

```python
RandomForestRegressor(
    n_estimators=300,
    max_depth=None,
    min_samples_split=2,
    random_state=42
)
```

### 8.5. Resultados y métricas

El modelo logró un rendimiento satisfactorio en el conjunto de prueba:

| Métrica  | Resultado   |
| -------- | ----------- |
| **MAE**  | ~380 pesos  |
| **RMSE** | ~1129 pesos |
| **R²**   | ~0.84       |

Esto indica que el modelo explica aproximadamente el 84% de la variabilidad del importe.

### 8.6. Conclusiones del modelo

- **cantidad** y **precio_unitario** son las variables con mayor impacto en la predicción.

- Las variables categóricas (**categoria_corregida**, **medio_pago**, **ciudad**) aportan información adicional útil.

- El modelo es adecuado como aproximación inicial y cumple plenamente los requisitos del proyecto académico.

### 8.7. Diagrama visual del flujo del modelo

```mermaid
flowchart TD

A[1. Objetivo del Modelo]
B[2. Carga y Selección Dataset<br/>Definir X e y]
C[3. Preprocesamiento<br/>- Filtrado importe>0<br/>- División num/cat<br/>- OneHot Encoding]
D[4. División Train/Test]
E[5. Entrenamiento<br/>Random Forest Regressor]
F[6. Predicción<br/>y_pred = modelo.predict]
G[7. Evaluación<br/>MAE - RMSE - R2]
H[8. Conclusiones Finales]

A --> B --> C --> D --> E --> F --> G --> H
```

### 8.8. Conclusiones Generales del Proyecto

El análisis completo de Tienda Aurelion permitió integrar múltiples fuentes de datos, corregir inconsistencias y construir una tabla unificada confiable para el estudio. A través del proceso de limpieza, EDA y modelización, se identificaron patrones relevantes en el comportamiento de los clientes, la composición de las ventas y la influencia de características específicas de los productos.

En la etapa de Machine Learning se desarrolló un modelo predictivo simple, orientado a estimar el importe final de una venta a partir de variables numéricas y categóricas. Tras aplicar preprocesamiento mediante codificación One-Hot y dividir los datos en entrenamiento y prueba, se entrenó un modelo Random Forest Regressor, el cual presentó un desempeño sólido para un enfoque introductorio, alcanzando valores satisfactorios de MAE, RMSE y R².

El flujo seguido aseguró transparencia y reproducibilidad: objetivo definido, dataset explicado, preprocesamiento claro, métricas explícitas y conclusiones sustentadas. En conjunto, este proyecto demuestra un pipeline analítico completo, coherente con los lineamientos del curso e ilustrativo del proceso real de trabajo en ciencia de datos.