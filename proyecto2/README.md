# Proyecto de Optimización de Ruteo de Vehículos (VRP) - Jupyter Notebook

Este proyecto implementa un modelo de optimización logística de rutas vehiculares usando **Pyomo** dentro de un **Jupyter Notebook**. Considera múltiples **centros de distribución**, **clientes con demanda**, y **vehículos con restricciones de capacidad y autonomía**, usando distancias reales calculadas con la API pública de **OSRM**.


## Contenido del repositorio

```

proyecto2
├── Proyecto-2.ipynb                # Notebook principal con todo el código integrado
├── data/                           # Carpeta para posibles archivos de entrada
├── resultados/
│   ├── caso1\_solucion.html         # Mapa generado para caso 1
│   ├── caso2\_solucion.html         # Mapa generado para caso 2
│   └── ruta\_optima\_folium.html     # Mapa general con rutas óptimas
└── README.md

```

## Cómo usar este proyecto

### 1. Requisitos

Instala las librerías necesarias ejecutando en una celda del notebook:

```python
!pip install pyomo folium requests
````

También necesitas tener instalado un solver como **GLPK**:

* En Linux/macOS:

  ```bash
  sudo apt install glpk-utils
  ```
* En Windows:
  Descarga e instala desde:
  [https://sourceforge.net/projects/winglpk/](https://sourceforge.net/projects/winglpk/)

### 2. Ejecución

1. Abre el archivo `Proyecto-2.ipynb` en Jupyter.
2. Ejecuta cada celda en orden:

   * Carga de datos
   * Cálculo de distancias y rutas (OSRM)
   * Construcción y resolución del modelo en Pyomo
   * Visualización con `folium`

### 3. Resultados

* Los mapas interactivos se guardan automáticamente en la carpeta `resultados/`, como archivos `.html`, y pueden abrirse en cualquier navegador.
* Las rutas optimizadas también se imprimen directamente en la salida del notebook.


## ¿Qué resuelve este modelo?

* Asigna rutas óptimas a una flota de vehículos.
* Garantiza que todos los clientes sean atendidos.
* Cumple restricciones de:

  * Capacidad de vehículos y centros
  * Autonomía de vehículos
  * Prevención de subrutas
  * Salida y retorno obligatorio a un centro



