⚡ El Negocio de la Lluvia
Análisis de datos meteorológicos y económicos sobre las interrupciones por protocolo de rayos en el fútbol profesional en EE.UU.
> *"503 minutos. $12.3 millones estimados. Dos partidos con cielo despejado según registros públicos. Un protocolo de seguridad que salva vidas — y que activa un monopolio temporal perfecto para las concesionarias."*
Blog: El Analista Incómodo | Artículo completo: El negocio de la lluvia
---
📋 Descripción del proyecto
Este repositorio contiene todos los datos, análisis y visualizaciones del artículo "El Negocio de la Lluvia", publicado en El Analista Incómodo.
El proyecto analiza 7 partidos del Mundial de Clubes 2025 y la Concachampions 2026 disputados en EE.UU. que fueron interrumpidos bajo el protocolo de rayos FIFA. Cruza registros meteorológicos oficiales con datos económicos para responder una pregunta simple:
> **¿El protocolo se activó cuando los datos públicos lo justifican?**
Este repositorio es abierto y replicable. Si encuentras errores, tienes datos adicionales o quieres refutar el análisis — bienvenido.
---
🗂️ Estructura del repositorio
```
el-negocio-de-la-lluvia/
│
├── 📁 datos/
│   ├── raw/
│   │   ├── metar/
│   │   │   ├── 17JUN25_KMCO_UlsanMamelodi.txt
│   │   │   ├── 18JUN25_KCVG_PachucaSalzburgo.txt
│   │   │   ├── 19JUN25_KTEB_PalmeiraAlAhly.txt
│   │   │   ├── 20JUN25_KMCO_BenficaAuckland.txt
│   │   │   ├── 24JUN25_KBNA_BocaAuckland.txt
│   │   │   ├── 28JUN25_KCLT_BenficaChelsea.txt
│   │   │   └── 28ABR26_KBNA_NashvilleTigres.txt
│   │   ├── noaa_ghcn/
│   │   │   └── [archivos GHCN-Daily por fecha y ciudad]
│   │   └── compass_group/
│   │       └── annual_report_2025.pdf
│   │
│   └── procesados/
│       ├── tabla_partidos.xlsx
│       ├── tabla_consumo.xlsx
│       ├── tabla_clima_horario.xlsx
│       ├── tabla_noaa_ghcn.xlsx
│       └── evidencia_meteorologica.xlsx
│
├── 📁 dashboard/
│   └── el_negocio_lluvia.pbix
│
├── 📁 imagenes/
│   ├── dashboard_el_negocio.png
│   └── dashboard_evidencia_clima.png
│
└── README.md
```
---
📊 Los 7 partidos analizados
Partido	Fecha	Estadio	Duración	Operador	Veredicto METAR
Ulsan vs Mamelodi Sundowns	17 Jun 2025	Inter&Co, Orlando	60 min	Levy	⚠️ Cuestionable
Pachuca vs Salzburgo	18 Jun 2025	TQL Stadium, Cincinnati	60 min	Levy	✅ Justificado
Palmeiras vs Al-Ahly	19 Jun 2025	MetLife, New Jersey	40 min	Delaware North	🔴 Sin evidencia directa
Benfica vs Auckland City	20 Jun 2025	Inter&Co, Orlando	120 min	Levy	🟡 Preventivo
Boca Juniors vs Auckland City	24 Jun 2025	GEODIS Park, Nashville	50 min	Levy	⚠️ Cuestionable
Benfica vs Chelsea	28 Jun 2025	Bank of America, Charlotte	113 min	Levy	🔴 Marginal
Nashville vs Tigres	28 Abr 2026	GEODIS Park, Nashville	60 min	Levy	❓ Indeterminado
Total: 503 minutos | Ingreso estimado: $10.8M – $12.5M
---
🌦️ Fuentes meteorológicas
Registros METAR (Iowa State Mesonet)
Datos horarios de condición atmosférica por estación ASOS — los mismos registros que usan los pilotos de aviación.
```
Fuente: https://mesonet.agron.iastate.edu/request/download.phtml
Red: ASOS (Automated Surface Observing System)
```
Partido	Estación	Código	Distancia al estadio
Ulsan vs Mamelodi / Benfica vs Auckland	Orlando Airport	KMCO	~8.5 millas
Pachuca vs Salzburgo	Cincinnati Airport	KCVG	~8 millas
Palmeiras vs Al-Ahly	Teterboro Airport	KTEB	3.29 millas
Boca vs Auckland / Nashville vs Tigres	Nashville Airport	KBNA	~8 millas
Benfica vs Chelsea	Charlotte Airport	KCLT	~7 millas
> **Nota metodológica:** Los METAR son observaciones de aeropuertos, no detectores de rayo de precisión. El protocolo FIFA usa sensores Vaisala NLDN — datos de acceso restringido. Un rayo puede caer dentro del radio de 8 millas sin aparecer en el METAR si la estación está a mayor distancia. Esta limitación está declarada en el artículo.
NOAA GHCN-Daily
```
Fuente: https://www.ncei.noaa.gov/cdo-web/
Variable clave: WT03 (Thunder — tormenta eléctrica registrada ese día)
```
---
💰 Metodología de estimación económica
El ingreso estimado durante cada parada se calculó con la siguiente fórmula:
```
Ingreso estimado = (Minutos de parada ÷ 60) × Asistencia oficial × Gasto por hora
```
Con tres escenarios de gasto por persona por hora:
Escenario	Gasto/persona/hora	Fuente
Conservador	$80 USD	Forbes / FIFA Industry Benchmark
Medio	$100 USD	Forbes / FIFA Industry Benchmark
Alto	$120 USD	Forbes / FIFA Industry Benchmark
> **Declaración importante:** Estos son estimados basados en benchmarks de industria. No son cifras reales de ventas. Levy Restaurants (Compass Group) y Delaware North no publican ingresos desagregados por evento.
Fuente corporativa
Compass Group PLC Annual Report 2025 — Sports & Leisure: $6,521M (dato auditado, cotiza en Londres LSE: CPG.L)
Delaware North — empresa privada, sin obligación de reportar
---
🔑 Hallazgos principales
Concentración de operador:
```
Levy Restaurants (Compass Group) → 6 de 7 partidos → 81% del ingreso estimado
Delaware North                   → 1 de 7 partidos → 19% del ingreso estimado
```
Análisis meteorológico cruzado:
```
✅ Claramente justificado:        1 de 7 (Pachuca vs Salzburgo)
🟡 Preventivo con base:           1 de 7 (Benfica vs Auckland)
⚠️ Cuestionable:                  2 de 7 (Ulsan, Boca)
🔴 Sin evidencia directa:         2 de 7 (Palmeiras, Benfica vs Chelsea)
❓ Indeterminado:                  1 de 7 (Nashville vs Tigres)
```
Caso más documentado:
Palmeiras vs Al-Ahly — la estación KTEB (Teterboro, 3.29 millas del MetLife) reportó código CLR (cielo despejado) 11 minutos después de la parada. La primera actividad eléctrica llegó 2 horas y 43 minutos después.
---
🛠️ Herramientas utilizadas
Herramienta	Uso
Microsoft Excel + Power Query	ETL y limpieza de datos
Power BI	Dashboard y visualizaciones
	
Iowa State Mesonet	Descarga de registros METAR
NOAA CDO	Descarga GHCN-Daily
---
📖 Cómo replicar el análisis
1. Descarga los datos meteorológicos
```
# Iowa State Mesonet — METAR por estación y fecha
https://mesonet.agron.iastate.edu/request/download.phtml

Selecciona:
→ Network: [Estado] ASOS
→ Station: KTEB / KMCO / KCVG / KBNA / KCLT
→ Fecha del partido
→ Variables: wxcodes, metar
→ Formato: CSV
```
2. Descarga los datos NOAA
```
https://www.ncei.noaa.gov/cdo-web/search

Selecciona:
→ Dataset: Daily Summaries
→ Variables: WT03 (Thunder), PRCP, WSF5
→ Estación más cercana a cada estadio
→ Fecha del partido
```
3. Abre el Excel de datos procesados
Todos los datos ya están limpios y listos en `datos/procesados/`
4. Abre el dashboard en Power BI
Requiere Power BI Desktop (gratuito):
```
https://powerbi.microsoft.com/desktop
```
---
⚠️ Limitaciones declaradas
Este análisis tiene limitaciones reales que el lector debe considerar:
Datos Vaisala NLDN: El protocolo FIFA usa sensores de detección de rayos de Vaisala — datos restringidos al gobierno de EE.UU. y organismos autorizados. Los registros METAR usados en este análisis son observaciones de aeropuerto, no detectores de rayo de alta precisión.
Distancia de estaciones: Ninguna estación ASOS está ubicada dentro de los estadios. La más cercana (KTEB para MetLife) está a 3.29 millas. Las demás entre 7 y 8.5 millas.
Ingreso estimado: Los $12.3M son una estimación metodológicamente declarada, no cifras reales de ventas. Los operadores no publican datos desagregados por evento.
Dos analistas, 4 desacuerdos: Dos analistas revisando los mismos 7 archivos METAR no coincidieron en 4 de 7 casos. Esa ambigüedad es estructural — no metodológica.
---
🤝 Cómo contribuir
Este repositorio es abierto. Puedes:
Refutar el análisis con datos que yo no tuve acceso
Ampliar el dataset con partidos adicionales
Corregir errores en la clasificación meteorológica
Aportar datos Vaisala si tienes acceso a ellos
Replicar el análisis para otros torneos o países
Abre un Issue o manda un Pull Request. O escríbeme directamente en Substack.
---
📜 Fuentes primarias citadas
Fuente	Tipo	URL
Iowa State Mesonet	Registros METAR	mesonet.agron.iastate.edu
NOAA GHCN-Daily	Datos climáticos diarios	ncei.noaa.gov/cdo-web
Compass Group Annual Report 2025	Reporte financiero auditado	compass-group.com/investors
NWS Lightning Safety	Protocolo oficial EE.UU.	weather.gov/safety/lightning
FIFA Laws of the Game	Protocolo FIFA	inside.fifa.com/official-documents
Sofascore / Transfermarkt	Asistencias oficiales	sofascore.com / transfermarkt.com
---
👤 Autor
Luis Alberto Becerril Bautista
Analista de datos | El Analista Incómodo
📧 Contacto: Substack
💼 LinkedIn: linkedin.com/in/tu-perfil
📊 Stack: Excel · Power Query · Power BI · SQL · Python · pandas
---
📄 Licencia
Los datos meteorológicos son públicos (gobierno de EE.UU.).
Los datos corporativos son de reportes auditados públicos.
El análisis, las visualizaciones y el código son de libre uso con atribución.
```
El Analista Incómodo — Donde los números dicen lo que nadie quiere leer.
```
