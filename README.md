# Sistema Inteligente de Transporte Urbano de Tunja 🚌

Actividad 2 — Búsqueda y sistemas basados en reglas
Inteligencia Artificial

## Introducción

El transporte público es uno de los escenarios más cotidianos donde las personas deben tomar decisiones basadas en información incompleta o dispersa: ¿qué ruta tomar?, ¿es necesario un transbordo?, ¿cuánto tiempo tomará el viaje? Este proyecto busca representar ese proceso de decisión mediante un **sistema basado en reglas**, uno de los enfoques más antiguos y didácticos dentro de la Inteligencia Artificial simbólica.

El sistema modela una versión simplificada del transporte urbano de Tunja (Boyacá), a partir de una **base de conocimiento** compuesta por lugares, rutas y tiempos estimados de viaje. Sobre esa base, el programa aplica un pequeño motor de inferencia construido con condicionales (`if`, `elif`, `else`) que evalúa dos reglas principales:

1. Si el origen y el destino pertenecen a la misma ruta, se recomienda una **ruta directa**.
2. Si no existe una ruta directa, el sistema busca dos rutas que compartan un punto en común y arma una **ruta con transbordo**.

Cuando ninguna de las dos reglas se cumple, el sistema informa al usuario que no fue posible encontrar una conexión con la información disponible.

El objetivo académico es demostrar, de forma sencilla y completamente comentada, cómo estructuras básicas de programación (listas, diccionarios, funciones y condicionales) pueden combinarse para simular un razonamiento lógico simple, similar al que usaría una persona al planear su viaje en la vida real.

## ¿Qué hace el sistema?

- Contiene una base de conocimiento con 21 lugares y 10 rutas del transporte urbano de Tunja.
- Le pide al usuario un lugar de origen y un lugar de destino.
- Busca primero una ruta directa entre ambos lugares.
- Si no la encuentra, busca una combinación de dos rutas (con un punto de transbordo en común).
- Muestra el recorrido paso a paso, el número de transbordos y el tiempo aproximado del viaje.
- Si no existe ninguna conexión registrada, se lo informa al usuario.

## Base de conocimiento

| Elemento | Descripción |
|---|---|
| `LUGARES` | Lista de los lugares/paraderos conocidos por el sistema |
| `RUTAS` | Diccionario donde cada ruta (`R1`, `R8`, `R9`, etc.) contiene la lista ordenada de lugares por los que pasa |
| `TIEMPOS` | Diccionario con el tiempo aproximado (en minutos) que toma cada ruta completa |

## Reglas del sistema

| Regla | Condición | Acción |
|---|---|---|
| Regla 1 | Origen y destino están en la misma ruta, en orden correcto | Recomendar ruta directa |
| Regla 2 | No hay ruta directa, pero dos rutas comparten un lugar en común | Recomendar ruta con transbordo |
| Regla 3 | Ninguna de las anteriores se cumple | Informar que no se encontró conexión |

## Estructura del repositorio

```
├── Transporte_Tunja.py     # Código fuente (también disponible como .ipynb de Colab)
├── README.md                # Este archivo
```

## Cómo ejecutarlo

1. Clona el repositorio o descarga el archivo `.py` / `.ipynb`.
2. Ejecútalo en Python 3 (o ábrelo directamente en Google Colab).
3. Cuando el programa lo solicite, escribe el nombre exacto de un lugar de origen y uno de destino (deben coincidir con los que aparecen en la lista `LUGARES`).
4. El sistema mostrará la ruta recomendada, el recorrido, los transbordos necesarios y el tiempo estimado.

## Conclusiones

- El desarrollo de este sistema permitió comprender de manera práctica cómo un conjunto de reglas lógicas simples, apoyadas en estructuras de datos básicas (listas y diccionarios), puede simular un proceso de toma de decisiones que en apariencia requeriría un análisis más complejo.
- Representar el conocimiento del dominio (lugares, rutas y tiempos) de forma separada de la lógica de búsqueda facilita que el sistema pueda crecer o corregirse sin tener que modificar el motor de reglas, lo cual es una de las ventajas centrales de los sistemas basados en reglas frente a soluciones "hardcodeadas".
- Se evidenció también una limitación propia de este enfoque: el sistema solo encuentra la primera solución que cumple las reglas, no necesariamente la más rápida o la más eficiente, lo que abre la puerta a mejoras futuras como comparar varias alternativas y escoger la de menor tiempo total, o considerar las rutas en ambos sentidos de circulación.
- En conjunto, la actividad permitió aplicar de forma concreta conceptos vistos en el curso —bases de conocimiento, reglas lógicas, condicionales, funciones y `return`— en un caso realista y cercano al contexto del estudiante: el transporte urbano de su propia ciudad.

## Autores
Natalia Espinosa y Eduard Rojas

Proyecto desarrollado como parte de la Actividad 2 del curso de Inteligencia Artificial — Búsqueda y sistemas basados en reglas.
