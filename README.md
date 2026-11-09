
# 📊 Evaluación del Desempeño Comercial y Cálculo de Bonos Trimestrales

### Business Intelligence | Sales Performance & Incentive Analytics

![Power BI](https://img.shields.io/badge/Power_BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![Excel](https://img.shields.io/badge/Excel-217346?style=for-the-badge&logo=microsoftexcel&logoColor=white)
![Business Intelligence](https://img.shields.io/badge/Business_Intelligence-2563EB?style=for-the-badge)
![Sales Analytics](https://img.shields.io/badge/Sales_Analytics-475569?style=for-the-badge)

---

## 📌 Descripción del proyecto

Este proyecto aborda un caso práctico de **evaluación del desempeño comercial y cálculo de incentivos trimestrales** en una empresa del sector asegurador.

A partir de información de 150 colaboradores, se plantea una solución analítica para evaluar el cumplimiento de metas de ventas, determinar la asignación de bonos según reglas de negocio y analizar la provisión económica requerida.

El ejercicio integra el procesamiento de información, la aplicación de criterios de compensación variable y la visualización de indicadores mediante Power BI.

El propósito es convertir los resultados comerciales en información estructurada que facilite el seguimiento del desempeño y la planificación de incentivos.

---

## 🏢 Contexto del negocio

**Escenario empresarial del caso**

Una empresa del sector asegurador cuenta con diferentes áreas funcionales y establece metas de ventas trimestrales para sus colaboradores.

Como parte de su política de incentivos, la organización asigna bonos económicos en función del porcentaje de cumplimiento de dichas metas.

Para determinar los bonos, se deben considerar tres variables principales:

- Meta trimestral asignada.
- Ventas efectivamente alcanzadas.
- Sueldo base mensual del colaborador.

El cálculo debe realizarse de manera consistente para los 150 empleados, respetando los rangos de cumplimiento establecidos.

### Problema de negocio

La evaluación individual del cumplimiento de metas y la asignación de incentivos requieren aplicar reglas uniformes a múltiples colaboradores.

En un proceso manual, la consolidación de resultados puede consumir tiempo y aumentar el riesgo de errores en la aplicación de los porcentajes de bonificación.

Adicionalmente, la información individual debe consolidarse para responder preguntas de gestión:

- ¿Qué porcentaje de colaboradores alcanzó sus metas?
- ¿Cuántos empleados califican para recibir un bono?
- ¿Cuál es el monto total que debe provisionarse?
- ¿Qué áreas presentan mayores niveles de cumplimiento?
- ¿Cómo se distribuye la provisión de bonos entre las áreas?

**Necesidad identificada:** disponer de un proceso de cálculo estandarizado y una herramienta analítica que permita evaluar el desempeño comercial y sus implicaciones económicas.

---

## 🎯 Objetivos del proyecto

### Objetivo general

Analizar el desempeño comercial de 150 colaboradores mediante el cálculo del cumplimiento de metas trimestrales y la asignación de bonos, proporcionando indicadores que apoyen la gestión de incentivos.

### Objetivos específicos

1. Calcular el porcentaje de cumplimiento de ventas por empleado.
2. Aplicar las reglas de bonificación establecidas.
3. Determinar el monto del bono correspondiente a cada colaborador.
4. Calcular la provisión total de bonos.
5. Consolidar resultados por área funcional.
6. Visualizar indicadores de desempeño y compensación variable.

---

# 🗂️ Descripción del dataset

El análisis utiliza el archivo `empleados_ventas.xlsx`, que contiene información de **150 empleados de una empresa de seguros**.

### Estructura de los datos

| Campo | Descripción |
|-------|-------------|
| ID Empleado | Identificador único del colaborador. |
| Nombre Completo | Nombre del empleado. |
| Área | Área funcional a la que pertenece. |
| Sueldo Base (S/) | Remuneración mensual del colaborador. |
| Meta Ventas Trimestre (S/) | Objetivo de ventas asignado para el trimestre. |
| Ventas Reales (S/) | Ventas efectivamente alcanzadas. |

### Características del dataset

- **Registros:** 150 empleados.
- **Variables:** 6 columnas.
- **Sector:** Seguros.
- **Moneda:** Soles peruanos (PEN).
- **Periodo:** Evaluación trimestral.
- **Fuente:** Dataset proporcionado para una evaluación práctica.

El archivo contiene una hoja `Empleados`, con los registros utilizados para el análisis, y una hoja `Instrucciones`, donde se especifican las reglas de bonificación.

---

# ⚙️ Reglas de negocio

Las reglas de negocio establecen cómo evaluar el cumplimiento de metas y determinar el incentivo económico correspondiente a cada empleado.

## Regla 1 — Cálculo del cumplimiento

El porcentaje de cumplimiento representa la relación entre las ventas reales y la meta trimestral asignada.

**Fórmula:**

Cumplimiento (%) = (Ventas Reales / Meta Trimestral) × 100

Por ejemplo, si un colaborador tiene:

- Meta trimestral: S/ 100,000
- Ventas reales: S/ 115,000

Su porcentaje de cumplimiento será:

Cumplimiento = (115,000 / 100,000) × 100

**Resultado: 115%**

Este porcentaje determina el tramo de bonificación que corresponde aplicar.

## Regla 2 — Asignación del bono

La empresa establece cuatro niveles de bonificación según el cumplimiento alcanzado.

| Nivel de cumplimiento | Condición | Bono asignado |
|-----------------------|-----------|---------------|
| Menor al mínimo | Cumplimiento < 80% | Sin bono |
| Cumplimiento parcial | 80% ≤ Cumplimiento < 100% | 50% del sueldo base |
| Meta alcanzada | 100% ≤ Cumplimiento < 120% | 100% del sueldo base |
| Sobrecumplimiento | Cumplimiento ≥ 120% | 150% del sueldo base |

### Interpretación

**Nivel 1 — Sin bonificación**

Los empleados cuyo cumplimiento sea inferior al 80% no reciben un incentivo económico.

**Nivel 2 — Bonificación parcial**

Los colaboradores que alcancen al menos el 80%, pero no lleguen al 100%, reciben un bono equivalente al 50% de su sueldo base.

**Nivel 3 — Cumplimiento de meta**

Los empleados que alcancen el 100% de la meta, sin llegar al 120%, reciben un bono equivalente al 100% de su sueldo base.

**Nivel 4 — Sobrecumplimiento**

Los colaboradores con un cumplimiento igual o superior al 120% reciben un bono equivalente al 150% de su sueldo base.

> El bono se calcula utilizando el sueldo base mensual indicado en el dataset, aunque la evaluación del desempeño corresponde al trimestre.

## Regla 3 — Cálculo del bono individual

El monto del bono se determina multiplicando el sueldo base por el factor correspondiente al nivel de cumplimiento.

**Fórmula:**

Bono = Sueldo Base × Factor de Bonificación

### Ejemplo práctico

Supongamos un colaborador con los siguientes datos:

| Variable | Valor |
|----------|-------|
| Sueldo base | S/ 4,000 |
| Meta trimestral | S/ 100,000 |
| Ventas reales | S/ 115,000 |
| Cumplimiento | 115% |
| Factor de bonificación | 100% |
| Bono correspondiente | S/ 4,000 |

El colaborador alcanza el 115% de su meta trimestral.

Según las reglas establecidas, pertenece al tramo de cumplimiento entre 100% y menos de 120%.

Por lo tanto:

Bono = 4,000 × 1.00

**Bono asignado: S/ 4,000**

*Ejemplo ilustrativo de aplicación de las reglas, no un registro específico del dataset.*

## Regla 4 — Provisión total de bonos

La provisión total representa la suma de los bonos calculados para todos los colaboradores.

**Fórmula:**

Provisión Total = Σ Bonos Individuales

Este indicador permite estimar el monto económico necesario para cubrir los incentivos del trimestre.

## Regla 5 — Consolidación por área

Los resultados deben agruparse según el área funcional de cada colaborador.

Esto permite obtener:

- Cantidad de empleados por área.
- Cantidad de empleados con y sin bono.
- Cumplimiento de metas por área.
- Provisión total de bonos por área.
- Distribución de incentivos entre áreas.

La agregación debe considerar las metas y ventas correspondientes a los empleados de cada área.

---

# 🔄 Proceso de solución

El ejercicio contempla un flujo de automatización, procesamiento y visualización de información.

```text
Recepción de archivos
        │
        ▼
Google Apps Script
Lectura de correos y adjuntos
        │
        ▼
Google Drive
Almacenamiento centralizado
        │
        ▼
Google Colab / Python
Procesamiento y aplicación de reglas
        │
        ▼
Archivo Excel de resultados
        │
        ▼
Power BI
Modelamiento y visualización
        │
        ▼
Indicadores de desempeño
y provisión de bonos
```

### Procesamiento de datos

La solución descrita para el ejercicio contempla:

1. Obtener los archivos de información comercial.
2. Centralizar los datos recibidos.
3. Calcular el cumplimiento de metas.
4. Asignar los factores de bonificación.
5. Determinar los bonos individuales.
6. Consolidar los resultados por área.
7. Generar información para el análisis y la visualización.

El documento de evaluación también describe un componente adicional en Python para análisis descriptivo, clasificación de empleados e identificación de anomalías.

---

# 📊 Indicadores de negocio

El análisis se organiza alrededor de los siguientes KPIs:

| Indicador | Propósito |
|-----------|-----------|
| Total de empleados | Identificar la población evaluada. |
| Cumplimiento de ventas | Medir el logro de metas comerciales. |
| Empleados con bono | Cuantificar los colaboradores que califican para incentivos. |
| Empleados sin bono | Identificar colaboradores por debajo del umbral mínimo. |
| Provisión total | Determinar el monto agregado de los incentivos. |
| Provisión por área | Comparar la distribución económica de los bonos. |
| Distribución por nivel de cumplimiento | Analizar la concentración de empleados en cada tramo de bonificación. |

---

# 📈 Dashboard de Power BI

El dashboard complementa el procesamiento de datos mediante visualizaciones orientadas al seguimiento de los indicadores comerciales.

![Dashboard de Desempeño Comercial](images/dashboard_preview.jpg)

El reporte permite analizar:

- Provisión total de bonos.
- Cumplimiento global de ventas.
- Cantidad de empleados con y sin bonificación.
- Comparaciones de resultados entre áreas.
- Distribución de indicadores mediante gráficos y filtros.

---

# 💡 Análisis y oportunidades de negocio

El modelo de bonificación permite evaluar el desempeño comercial desde dos perspectivas:

**1. Desempeño de los colaboradores**

La clasificación por niveles de cumplimiento permite identificar qué empleados alcanzan las metas, cuáles las superan y cuáles se encuentran por debajo del umbral mínimo.

Esta información puede apoyar el seguimiento de objetivos comerciales y la identificación de oportunidades de acompañamiento.

**2. Impacto económico de los incentivos**

El cálculo de la provisión permite conocer la obligación económica estimada derivada de las reglas de bonificación.

La consolidación por área facilita la comparación de incentivos y la planificación de recursos.

### Recomendaciones de gestión

- Realizar seguimiento periódico del cumplimiento de metas.
- Analizar las diferencias de desempeño entre áreas.
- Identificar colaboradores que se encuentran próximos a alcanzar un nuevo tramo de bonificación.
- Validar los cálculos de incentivos antes de su aprobación.
- Comparar la provisión calculada con el presupuesto disponible.
- Automatizar controles para detectar errores o inconsistencias en los datos.

Estas recomendaciones se derivan del caso y de sus reglas de negocio; no representan acciones implementadas por la empresa.

---

# 📚 Aprendizajes del ejercicio

El desarrollo del caso permitió aplicar conceptos relacionados con:

- **Reglas de negocio:** transformar políticas de incentivos en condiciones de cálculo.
- **Procesamiento de datos:** estructurar y consolidar información comercial.
- **Business Intelligence:** construir indicadores para evaluar el desempeño.
- **Automatización:** diseñar un flujo que reduzca tareas repetitivas.
- **Análisis empresarial:** relacionar el cumplimiento de metas con el impacto económico de los bonos.

---

## 📁 Estructura del repositorio

```text
sales-performance-bonus-dashboard/
│
├── README.md
│
├── images/
│   └── dashboard_preview.jpg
│
├── powerbi/
│   └── dashboard_comercial.pbix
│
└── datos/
    └── empleados_ventas.xlsx
```

Los archivos deben revisarse antes de su publicación para evitar divulgar información personal o empresarial no autorizada.

---

## 👨‍💻 Autor

**Erick Jauregui**

Estudiante de Ingeniería de Sistemas de Información, con interés en Análisis de Datos, Business Intelligence y automatización de procesos.

🌐 **Portafolio:** [jaureguierick.netlify.app](https://jaureguierick.netlify.app/)

---

⭐ *Ejercicio práctico de analítica comercial orientado a la evaluación del desempeño, aplicación de reglas de negocio y gestión de incentivos trimestrales.*
