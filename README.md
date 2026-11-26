# Simulador de Metalurgia de la Soldadura

[![Demo en vivo](https://img.shields.io/badge/Demo-GitHub%20Pages-1d6fa5?style=flat-square&logo=github)](https://sosomedi.github.io/Simulador-Metalurgia-de-la-Soldadura/)
[![HTML5](https://img.shields.io/badge/HTML5-Single--File-e34f26?style=flat-square&logo=html5&logoColor=white)](#tecnologías)
[![JavaScript](https://img.shields.io/badge/JavaScript-Vanilla%20ES6-f7df1e?style=flat-square&logo=javascript&logoColor=black)](#tecnologías)

Simulador interactivo web desarrollado para el curso de **Metalurgia de la Soldadura** (Universidad de Antioquia). Permite modelar y comparar en tiempo real dos procedimientos de soldadura desde el diagrama de fases hasta la microestructura de la junta, los modos de solidificación, los riesgos de agrietamiento y los cálculos paso a paso.

 **Pruébalo en vivo aquí:** [https://sosomedi.github.io/Simulador-Metalurgia-de-la-Soldadura/](https://sosomedi.github.io/Simulador-Metalurgia-de-la-Soldadura/)

---

## Sistemas de aleaciones y casos precargados

El simulador incluye cuatro diagramas de fases interactivos y cinco casos de estudio basados en evaluaciones del curso:

| Caso de estudio | Sistema | Procesos | Aplicación / Enfoque |
| :--- | :--- | :--- | :--- |
| **Parcial 3 (10/07/2025)** | $\text{Al–Mg}$ | GTAW | Chasis de vehículo eléctrico ($15\,\%\text{ Mg}$, aporte ER5356, solubilizado + $30\,\%$ en frío). |
| **Parcial 2020** | $\text{Al–Mg}$ | GTAW | Comparación de aleaciones ($0{,}9\,\%$, $16\,\%$ y $33\,\%\text{ Mg}$) con aporte $T_s = 7\,\%$. |
| **Supletorio (26/11/2025)** | $\text{Fe–Fe}_3\text{C}$ | SMAW | Vigas I de puente en ASTM A913 Gr.65 ($50\text{ mm}$, E8018-C3, $CE$, Seferian y $t_{8/5}$). |
| **Parcial C17000** | $\text{Cu–Be}$ | GTAW vs. PAW | Reparación de insertos de moldes (RCuBe-S, deformado en frío + envejecido). |
| **Parcial 4 (17/11/2026)** | $\text{Al–Cu}$ (AA2219) | GTAW | Tanques criogénicos ($\text{LH}_2$/$\text{LOX}$), comparación de estado de entrega O vs. T87 con ER2319. |

---

## Módulos principales

La interfaz está organizada en una barra lateral de parámetros editables (composición, aporte estándar o personalizado, procesos GTAW/PAW/SMAW/GMAW, estado de entrega y umbrales) y cinco pestañas de análisis:

### a) Diagrama de fases y microestructura
* **Diagrama interactivo:** clic o arrastre directo sobre el lienzo para explorar composición ($C_0$) y temperatura ($T$).
* **Regla de la palanca:** cálculo automático de fracciones de fase, composiciones y microconstituyentes.
* **Simulación microestructural (Voronoi):** visualización a escala ($\mu\text{m}$) tanto en equilibrio a la temperatura $T$ como en el estado de entrega (deformación en frío, precipitación, tamaño de grano ASTM E112).
* Ruta de enfriamiento lento y mecanismos de endurecimiento aplicables.

### b · c) Zona Fundida (ZF)
* **Morfología del charco:** vista superior comparativa de dos procedimientos con transición continua entre charco elíptico y en gota según la velocidad de avance ($v$) y ángulo de cola ($\alpha$).
* **Modos de solidificación:** transición plano $\rightarrow$ celular $\rightarrow$ dendrítico columnar $\rightarrow$ dendrítico equiaxial en función del soluto total, dilución ($\delta$) y relación $G/R$.
* **Microsegregación (Scheil):** visualización opcional de soluto rechazado ($k < 1$) y precipitados en contornos de grano, espacios interdendríticos y línea central.
* **Mapa $G\text{–}R$:** cálculo de gradiente térmico $G = (T_{\text{máx}} - T_S)/d$, velocidad de solidificación $R = v\cos\theta$, relación de forma ($G/R$) y velocidad de enfriamiento ($G \cdot R$).

### d) Perfil de la junta ($\text{ZF} \rightarrow \text{MB}$)
* **Temperatura pico $T_p(x)$:** modelado con la ecuación de Rosenthal para placa gruesa y lectura interactiva al pasar el cursor.
* **Subzonas de la ZAT:** identificación y ancho estimado de ZPF (criterio $\Delta T \ge 70\,^\circ\text{C}$), ZCG, ZRC, ZPT, ZSC, ZRS, ZSE, ZE y recuperación según el estado de entrega.
* **Franja microestructural y resistencia relativa:** representación continua desde los granos columnares epitaxiales de la ZF hasta el metal base, resaltando la zona más crítica.

### e) Riesgos de falla y discontinuidades
* Evaluación cualitativa comparativa con causas y medidas de prevención: agrietamiento por solidificación, licuación, inducido por hidrógeno (HIC), desgarre laminar, ablandamiento/sobreenvejecimiento de la ZAT, porosidad y corrosión intergranular.
* Tabla de discontinuidades esperables por proceso basada en AWS B1.10.

### $\Sigma$) Cálculos paso a paso (Modo estudio)
* Desarrollo numérico completo de aporte térmico neto ($H$), dilución, regla de la palanca, parámetros $G$ y $R$, radios de Rosenthal, criterio de ZPF, carbono equivalente ($CE$), precalentamiento (Seferian), tiempo de enfriamiento $t_{8/5}$ (2D/3D) y tamaño de grano ASTM.
* Incluye un botón para **ocultar resultados** y revelarlos uno a uno con un clic para practicar antes de los exámenes.

---

## Cómo usarlo

### Opción 1: En línea (recomendada)
Abre directamente la versión publicada en GitHub Pages:
[https://sosomedi.github.io/Simulador-Metalurgia-de-la-Soldadura/](https://sosomedi.github.io/Simulador-Metalurgia-de-la-Soldadura/)

### Opción 2: En local (sin conexión)
Al ser una aplicación autocontenida en un solo archivo, no requiere instalación ni servidor:
1. Clona el repositorio o descarga el archivo `index.html`:
   ```bash
   git clone https://github.com/sosomedi/Simulador-Metalurgia-de-la-Soldadura.git
   ```
2. Haz doble clic sobre `index.html` para abrirlo en cualquier navegador moderno (Chrome, Firefox, Edge o Safari).

---

## 🛠️ Tecnologías

* **HTML5 + CSS3 + JavaScript (ES6+)** en un único archivo sin dependencias ni *bundlers*.
* **Canvas 2D API** para el renderizado de diagramas de fases, microestructuras por teselación de Voronoi, charcos de soldadura y perfiles térmicos.

---

## Autor

Desarrollado por **Sosomedi** ([@sosomedi](https://github.com/sosomedi)) — Curso de Metalurgia de la Soldadura, Universidad de Antioquia.
