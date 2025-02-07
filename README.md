# Solución del Laboratorio No. 02 - Robótica Industrial

## Introducción
En este laboratorio, se analizó el manipulador industrial Motoman MH6, comparándolo con el ABB IRB140, y se realizaron diversas operaciones manuales y simulaciones utilizando el software RoboDK. A continuación, se presenta la solución paso a paso de cada una de las tareas asignadas.

---

## 1. Comparación de Especificaciones Técnicas

### Cuadro Comparativo: Motoman MH6 vs. ABB IRB140

| Característica          | Motoman MH6               | ABB IRB140               |
|-------------------------|---------------------------|--------------------------|
| Carga Máxima            | 6 kg                      | 6 kg                     |
| Alcance Máximo          | 1422 mm                   | 810 mm                   |
| Grados de Libertad      | 6                         | 6                        |
| Velocidad Máxima        | 6000 mm/s                 | 4500 mm/s                |
| Aplicaciones Típicas    | Soldadura, ensamblaje     | Pick and place, ensamblaje|

**Análisis:**
- El Motoman MH6 tiene un mayor alcance (1422 mm) en comparación con el IRB140 (810 mm), lo que lo hace más adecuado para aplicaciones que requieren mayor cobertura.
- Ambos robots tienen una carga máxima similar, pero el Motoman MH6 es más rápido (6000 mm/s) que el IRB140 (4500 mm/s).

---

## 2. Configuraciones Iniciales: Home1 y Home2 del Motoman MH6

### Descripción de Home1 y Home2
- **Home1**: Es la posición inicial predeterminada del robot, donde todas las articulaciones están en un estado neutral. Es útil para tareas generales.
- **Home2**: Es una posición alternativa que se configura para tareas específicas, como evitar obstáculos o optimizar el movimiento.

**Posición de las Articulaciones:**
- **Home1**: 
  - Articulación 1: 0°
  - Articulación 2: 0°
  - Articulación 3: 0°
  - Articulación 4: 0°
  - Articulación 5: 0°
  - Articulación 6: 0°
  
- **Home2**: 
  - Articulación 1: 90°
  - Articulación 2: -45°
  - Articulación 3: 45°
  - Articulación 4: 0°
  - Articulación 5: 0°
  - Articulación 6: 0°

**Justificación:**
- **Home1** es mejor para tareas generales, ya que permite un movimiento más libre y neutral. **Home2** es útil cuando se requiere una posición específica para evitar colisiones o para optimizar el tiempo de ciclo.

---

## 3. Movimientos Manuales del Manipulador Motoman MH6

### Procedimiento para Movimientos Manuales
1. **Cambiar entre modos de operación**:
   - **Modo Articulaciones**: Presionar la tecla `J1` a `J6` para mover cada articulación individualmente.
   - **Modo Cartesianos**: Presionar la tecla `X`, `Y`, o `Z` para mover el efector final en los ejes cartesianos.
   - **Traslaciones y Rotaciones**: Usar las teclas de flecha para mover el efector final en los ejes X, Y, Z, y las teclas `R1`, `R2`, `R3` para rotaciones.

2. **Realizar movimientos**:
   - Para mover el robot, mantener presionada la tecla correspondiente mientras se observa el movimiento en la pantalla.

---

## 4. Control de Velocidad en Movimientos Manuales

### Niveles de Velocidad
- El Motoman MH6 tiene 5 niveles de velocidad para movimientos manuales: **Lento**, **Medio-Lento**, **Medio**, **Medio-Rápido**, y **Rápido**.

### Cambio de Niveles de Velocidad
1. Presionar la tecla `VEL` para cambiar entre niveles de velocidad.
2. El nivel de velocidad actual se muestra en la pantalla del controlador.

---

## 5. Software RoboDK: Funcionalidades y Comunicación con el Manipulador

### Aplicaciones Principales de RoboDK
- **Simulación de trayectorias**: Permite diseñar y simular trayectorias antes de ejecutarlas en el robot físico.
- **Generación de código**: RoboDK genera automáticamente el código necesario para ejecutar las trayectorias en el robot.
- **Comunicación con el robot**: RoboDK se comunica con el robot a través de una conexión Ethernet o USB, enviando comandos de movimiento.

### Proceso para Mover el Manipulador
1. Diseñar la trayectoria en RoboDK.
2. Simular la trayectoria en el entorno virtual.
3. Exportar el código generado al controlador del robot.
4. Ejecutar la trayectoria en el robot físico.

---

## 6. Comparación entre RoboDK y RobotStudio

### Diferencias y Usos
| Característica          | RoboDK                     | RobotStudio               |
|-------------------------|----------------------------|---------------------------|
| Facilidad de uso        | Más intuitivo              | Menos intuitivo           |
| Compatibilidad          | Compatible con múltiples marcas de robots | Específico para robots ABB |
| Simulación              | Más rápida y flexible      | Más detallada pero lenta  |
| Costo                   | Más económico              | Más costoso               |

**Análisis:**
- **RoboDK** es más adecuado para usuarios que necesitan una herramienta rápida y flexible para múltiples marcas de robots.
- **RobotStudio** es ideal para usuarios que trabajan exclusivamente con robots ABB y requieren simulaciones más detalladas.

---

## 7. Trayectoria Polar en RoboDK

### Diseño y Ejecución de una Trayectoria Polar
1. **Diseño en RoboDK**:
   - Crear una trayectoria polar utilizando las herramientas de RoboDK.
   - Simular la trayectoria en el entorno virtual.

2. **Ejecución en el Robot Físico**:
   - Exportar el código generado al controlador del Motoman MH6.
   - Ejecutar la trayectoria en el robot físico.

### Código de Ejemplo en RoboDK
```python
# Código generado en RoboDK para una trayectoria polar
movej([0, 0, 0, 0, 0, 0], a=1.2, v=1.0)
movel([100, 0, 0], a=1.2, v=1.0)
movel([100, 100, 0], a=1.2, v=1.0)
