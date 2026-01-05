# Método de Yoshida: Simulación Gravitacional de 10 Cuerpos

Este repositorio contiene una implementación del **Método de Yoshida**, un integrador de alto orden diseñado para la simulación precisa de sistemas Hamiltonianos. Se aplica aquí para resolver la dinámica de un sistema gravitacional de 10 cuerpos en interacción mutua.



## 🌌 Descripción Teórica
A diferencia de los métodos de integración estándar (como Runge-Kutta), el algoritmo de Yoshida preserva la estructura del espacio de fases. Esto garantiza que los errores en la energía total del sistema no crezcan linealmente con el tiempo, permitiendo integraciones estables y precisas en simulaciones de largo plazo.

El integrador se basa en la técnica de composición desarrollada por **Haruo Yoshida**, donde un integrador básico de salto de rana (*leapfrog*) se aplica a varios intervalos de tiempo específicos. Al utilizar la secuencia correcta de pasos, los errores de orden inferior se compensan, permitiendo generar fácilmente un integrador de 4º orden.

### Características principales:
* **Integrador de Alto Orden:** Implementación de 4º orden basada en coeficientes de Yoshida.
* **Conservación de Energía:** Estabilidad superior del Hamiltoniano frente a métodos no conservativos.
* **Problema de N-cuerpos:** Modelado de 10 cuerpos con interacción gravitatoria completa.
* **Visualización:** Generación de animaciones 3D de las trayectorias mediante **PyVista** y **Matplotlib**.

---

## Generación de Datos
Los archivos de resultados no se incluyen en el repositorio debido a su tamaño (~1 GB en total).

> **Instrucciones:** Para realizar las visualizaciones y animaciones, ejecuta primero el notebook `main.ipynb`. Este generará automáticamente los archivos `momentos.npz` y `posiciones.npz` en el directorio resultados. Una vez generados, los scripts de visualización los detectarán de forma automática.

---

##  Requisitos
Para ejecutar este proyecto, necesitas tener instalado:
* Python 3.x
* NumPy
* Matplotlib (para las animaciones y gráficas)
* PyVista (para la visualización 3D)

```python
# Ejemplo rápido para cargar los datos una vez generados
import numpy as np
posiciones = np.load('posiciones.npz')
print(posiciones.files)
