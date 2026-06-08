# 📱 Análisis de Comportamiento de Usuarios — ConnectaTel 2024

## 🧩 Contexto del negocio
Como analista de datos en ConnectaTel, empresa de telecomunicaciones con operaciones en México y Colombia, el objetivo es construir un perfil estadístico de los clientes, detectar comportamientos atípicos y crear segmentos de usuarios para optimizar la oferta comercial.

## 🎯 Preguntas de negocio
1. ¿Qué segmentos muestran mayor o menor uso de llamadas y mensajes?
2. ¿Qué usuarios presentan valores atípicos o comportamientos inusuales?
3. ¿Cómo varía el uso según edad y tipo de plan contratado?
4. ¿Qué patrones ayudan a diseñar mejores planes?

## 🚀 Análisis Extendido — Iniciativa Propia
Adicional a los entregables del proyecto, se plantearon 3 preguntas de negocio propias:
- ¿Los usuarios con churn_date se concentran en algún plan específico?
- ¿Cómo se conforman los planes Básico y Premium por nivel de uso y edad?
- ¿Cómo es la distribución geográfica de los usuarios?

## 🛠️ Herramientas y librerías
- **Python** — pandas · numpy · seaborn · matplotlib
- **Jupyter Notebook** — pipeline completo documentado
- **Fuentes:** plans.csv · users_latam.csv · usage.csv

## 🔍 Pipeline de análisis
1. **Ingesta y EDA** — Carga e inspección estructural de 3 fuentes
2. **Auditoría de calidad** — Detección de nulos, sentinels y fechas fuera de rango
3. **Limpieza** — Imputación de sentinels, corrección MAR y fechas
4. **Perfil estadístico** — Agregación de métricas de uso por usuario
5. **Visualización y outliers** — Histogramas, boxplots y cappeo IQR
6. **Segmentación** — Por nivel de uso y grupo etario
7. **Insight ejecutivo** — Recomendaciones comerciales accionables
8. **Análisis extendido** — 3 preguntas adicionales por iniciativa propia

## 💡 Hallazgos principales
- El perfil predominante es **Adulto con Uso Medio**, núcleo comercial más estable de ConnectaTel
- Existe una oportunidad de **up-selling no capitalizada**: más usuarios de Alto Uso están en plan Básico que en Premium
- El **63.95% de cancelaciones** ocurre en plan Básico, proporcional a su tamaño pero accionable mediante campañas de retención
- **Bogotá** concentra la mayor base de usuarios (~800) y la mayor cantidad de usuarios Premium (~300)

## 🎯 Recomendaciones estratégicas
1. **Up-selling:** Campaña de migración para usuarios de Alto Uso en plan Básico hacia Premium
2. **Retención:** Programa enfocado en clientes Básico para reducir churn
3. **Add-ons:** Paquetes de minutos adicionales para usuarios con consumo extremo de llamadas
4. **Expansión geográfica:** Campañas de adquisición en GDL, Cali y MTY

## 📁 Archivos del repositorio
- `connectatel_analisis.ipynb` — Pipeline completo de análisis
- `user_profile_completo.csv` — Dataset final con perfiles y segmentos

## ⚠️ Nota sobre calidad de datos
- `city`: 11.73% nulos + sentinel `"?"` → imputados por `"unknown"`
- `age`: Sentinel `-999` → imputado por mediana
- `reg_date`: Fechas en año 2026 (~1%) → corregidas a 2024
- `duration` y `length`: Nulos MAR condicionados por `type` → conservados
