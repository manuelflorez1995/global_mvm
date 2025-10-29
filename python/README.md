# 🌎 Proyecto Global MVM

## 📋 Descripción
Este repositorio contiene los scripts y notebooks desarrollados como parte del **Reto de Ingeniería de Datos + Cloud**, cuyo objetivo principal fue simular un flujo de datos empresarial mediante la generación y almacenamiento de información estructurada.

En esta entrega se desarrollaron los **Desafíos 1 y 2**, enfocados en la creación de datos sintéticos y su persistencia en formato CSV.

---

## 🧩 Desafíos Desarrollados

### 🔹 Desafío 1: Generación Automática de Datos
Se construyó un script en Python que genera tres datasets relacionados:
- **Departamentos:** catálogo base con códigos y nombres.  
- **Puestos:** asociados a cada departamento, con rangos salariales.  
- **Empleados:** información de 400 empleados simulados con relaciones coherentes entre las llaves foráneas.

Archivos generados:
| Archivo | Descripción |
|----------|-------------|
| `departamento.csv` | Contiene los códigos y nombres de los departamentos. |
| `puestos.csv` | Define los puestos de trabajo y sus rangos salariales. |
| `empleados.csv` | Registra la información de empleados, incluyendo departamento, puesto y salario. |

---

### 🔹 Desafío 2: Almacenamiento y Formato de Datos
Los datos generados se exportaron en formato **CSV**, con el propósito de garantizar su **portabilidad, legibilidad y compatibilidad** con diversas herramientas locales.  

No obstante, en escenarios de **Big Data** o procesamiento masivo de información, se recomienda utilizar el formato **Parquet**, ya que ofrece **mayor eficiencia en almacenamiento, compresión y velocidad de lectura** para volúmenes de datos de gran escala.

| Criterio | CSV | Parquet |
|-----------|-----|----------|
| **Facilidad de uso** | Alta: compatible con Excel, Power BI, bases SQL | Requiere librerías adicionales |
| **Peso y compresión** | Mayor tamaño | Menor tamaño (compresión columnar) |
| **Uso recomendado** | Procesos simples o cargas manuales | Procesos analíticos masivos o Data Lake |

---

## ☁️ Arquitectura Referencial Propuesta
Aunque la implementación en la nube no se realizó por motivos de costo, se diseñó una **arquitectura lógica en Azure** para una futura ampliación del proyecto:

**Flujo de datos:**
1. **Data Source (Flat files)** → Archivos CSV generados localmente.  
2. **Azure Blob Storage** → Capa de almacenamiento en la nube.  
3. **Azure Data Factory** → Orquestación de procesos ETL.  
4. **Azure Database for PostgreSQL** → Almacenamiento estructurado y consultas analíticas.  
5. **Power BI Service** → Capa de consumo y visualización.

*(Ver diagrama en la carpeta `docs/arquitectura.png` o imagen adjunta en el informe.)*

---

## ⚙️ Tecnologías Utilizadas
| Componente | Descripción |
|-------------|-------------|
| **Lenguaje** | Python 3.10 |
| **Librerías** | pandas, numpy, faker |
| **Entorno** | Jupyter Notebook (`test_test.ipynb`) |
| **Formato de salida** | CSV (archivos planos) |
| **Arquitectura Cloud Referencial** | Azure Blob Storage + Data Factory + PostgreSQL + Power BI |

---

## 🗂️ Estructura del Proyecto
global_mvm/
├─ data/ # Archivos generados (CSV)
├─ src/ # Scripts Python
│ ├─ 01_generate_data.py
│ └─ 02_load_sqlite.py
├─ notebooks/
│ └─ test_test.ipynb
├─ docs/
│ └─ arquitectura.png
└─ README.md