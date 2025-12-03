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
