Retail Analytics Lab & Benchmark Simulator
Descripción General


Retail Analytics Lab es un laboratorio de inteligencia retail sin backend, completamente ejecutado en el lado del cliente. Esta plataforma está diseñada para decodificar la psicología del consumidor y el rendimiento operativo en distintos sectores comerciales mediante modelado interactivo.

A diferencia de las aplicaciones SaaS tradicionales que requieren infraestructura backend, este proyecto utiliza Stlite para compilar un entorno Python completo dentro del navegador mediante WebAssembly (Pyodide). Esto garantiza 0 MB de uso de disco en servidores, baja huella de memoria y despliegue estático instantáneo a través de GitHub Pages.

Arquitectura

text
[Navegador Cliente]
       │
       ├──> Stlite (Pyodide / WebAssembly)
       │      ├──> Streamlit Runtime (Python)
       │      ├──> Pandas (Manipulación de datos)
       │      └──> Plotly (Gráficos interactivos)
       │
       └──> GitHub Pages 
       
Modelo Matemático Principal
Las proyecciones económicas del simulador se basan en la ecuación fundamental del retail:

Facturación = Tráfico (visitas/h) × Horas × (Conversión (%) / 100) × AOV (€)

La eficiencia operativa se evalúa mediante UPT (Unidades Por Transacción):

Artículos Vendidos = Compradores Totales × UPT

Características Principales
1. Mapeo Psicológico (Gráfico de Burbujas)
Visualiza la relación inversa entre Tráfico (eje X) y Ticket Medio - AOV (eje Y)

Tamaño de burbuja refleja dinámicamente la Tasa de Conversión (%)

Separa sectores de alta fricción/alto margen (Lujo, Tecnología) de sectores de baja fricción/alto volumen (Alimentación, Bricolaje)

2. Simulador Financiero y Embudo de Conversión
Controles deslizantes interactivos para ajustar palancas operativas (Tráfico, Conversión, AOV, UPT) en tiempo real durante un turno de 8 horas

Gráfico de embudo Plotly que rastrea la tasa de abandono desde Visitas Totales → Compradores Reales → Artículos Vendidos

Generador de Insights para LinkedIn: formato resumido optimizado para networking ejecutivo

3. Editor Dinámico e Importación de Datos
Editor de datos integrado (st.data_editor) que permite modificación en vivo de benchmarks sectoriales

Pipeline de importación compatible con archivos CSV y Excel (.xlsx)

Capacidad de exportación para descargar parámetros activos

4. Segmentación Internacional
Selectores de mercado regional (España, EE.UU., Latinoamérica, Europa Central)

Aplicación automática de multiplicadores de poder adquisitivo y tráfico a los modelos base

Motor de Gobernanza Criptográfica y Auditoría
Para mantener el rigor académico y profesional, la plataforma incluye un rastreador de auditoría inmutable:

Hashing SHA-256: Cada configuración activa se convierte en un flujo de bytes CSV normalizado y se procesa mediante una función hash criptográfica. Cambiar un solo dato numérico altera la huella hash, garantizando la integridad de los datos.

Registros de Auditoría: Los usuarios pueden declarar fuentes de datos y justificaciones para modificaciones de benchmarks, generando un registro de cumplimiento exportable.

Stack Tecnológico
Frontend / Hosting: GitHub Pages (Hosting Web Estático)

Motor de Ejecución: Stlite Mountable (@0.59.0) ejecutando Python 3.x mediante WebAssembly

Procesamiento de Datos: pandas, openpyxl

Visualización de Datos: plotly.express, plotly.graph_objects

Seguridad y Hashes: hashlib de Python estándar (SHA-256)

Despliegue Local
Dado que toda la aplicación se ejecuta en el lado del cliente dentro de un único archivo (index.html), puedes ejecutarla localmente sin instalar Python o configurar entornos virtuales:

Clona el repositorio:

bash
git clone https://github.com/joseasenjo/retail-analytics-lab.git
cd retail-analytics-lab
Abre index.html directamente en cualquier navegador moderno (Chrome, Firefox, Edge, Safari), o sírvelo localmente usando un servidor HTTP básico:

bash
python3 -m http.server 8000
Navega a http://localhost:8000 en tu navegador.

Autor
Desarrollado por: Jose Luis Asenjo

Proyecto: Retail Analytics Lab & Benchmark Simulator (COP Lab v4 Architecture)

Enlaces
Repositorio GitHub: https://github.com/joseasenjo/retail-analytics-lab

Sitio en vivo: https://joseasenjo.github.io/retail-analytics-lab/

Artículo en LinkedIn:https://www.linkedin.com/feed/update/urn:li:activity:7487557933996785665/ 

Portfolio: https://joseasenjo.github.io/portfolio/

