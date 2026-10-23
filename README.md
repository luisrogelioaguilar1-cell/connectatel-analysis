# ConnectaTel | Análisis de clientes y patrones de consumo

**Proyecto final — Sprint 7 | TripleTen · Análisis de Datos**

## Descripción del proyecto

Este proyecto analiza información de clientes y eventos de uso de ConnectaTel para comprender sus hábitos de comunicación, identificar segmentos relevantes y proponer oportunidades de mejora de los planes de servicio. El análisis se realizó en Python mediante un notebook de Jupyter.

## Objetivo

- Evaluar la calidad de los datos e identificar inconsistencias.
- Describir el comportamiento de los clientes a partir de llamadas, mensajes y minutos de llamada.
- Segmentar usuarios por edad y nivel de uso.
- Detectar consumos atípicos y analizar sus implicaciones.
- Formular recomendaciones comerciales basadas en los resultados.

## Datos utilizados

| Archivo | Contenido | Registros originales |
|---|---|---:|
| `plans.csv` | Información de los planes de servicio | 2 |
| `users_latam.csv` | Perfil de clientes, edad, ciudad, fechas y plan | 4,000 |
| `usage.csv` | Eventos de llamadas y mensajes | 40,000 |

En el entorno de TripleTen, los archivos se consultaron desde la carpeta `/datasets/`.

> **Nota:** Los archivos CSV no se incluyen automáticamente en este repositorio. Para reproducir el análisis es necesario disponer de ellos y ajustar sus rutas si se ejecuta fuera del entorno de TripleTen.

## Herramientas

- Python
- pandas y NumPy
- Matplotlib y Seaborn
- Jupyter Notebook

## Etapas del análisis

1. **Exploración:** revisión de la estructura, los tipos de datos y los valores faltantes.
2. **Limpieza:** tratamiento de edades inválidas, ciudades no identificadas y fechas inconsistentes; revisión de campos de uso según el tipo de evento.
3. **Agregación:** cálculo de llamadas, mensajes y minutos por usuario.
4. **Análisis exploratorio:** estadísticas descriptivas y visualizaciones de consumo.
5. **Segmentación:** clasificación por edad y por intensidad de uso.
6. **Valores atípicos:** identificación mediante diagramas de caja y rango intercuartílico (IQR).
7. **Informe ejecutivo:** interpretación de hallazgos y recomendaciones para ConnectaTel.

## Principales hallazgos

- El **uso medio** es el comportamiento predominante en los tres grupos de edad estudiados: jóvenes (**72.63%**), adultos (**74.37%**) y adultos mayores (**72.91%**).
- Los adultos presentan la mayor proporción relativa de clientes de **alto uso** (**7.59%**), frente a jóvenes (**6.71%**) y adultos mayores (**6.06%**).
- Se detectaron **565 ciudades sin identificar** (**14.13%** de los usuarios), **40 fechas de registro en 2026** (**1%**) fuera del periodo histórico considerado y **50 eventos de uso sin fecha válida** (**0.125%**).
- Se observaron consumos extremos, especialmente en los minutos de llamada, cuyo valor máximo fue **155.69 minutos**. Se conservaron estos registros porque no se encontró evidencia suficiente para considerarlos errores.

**Alcance de las conclusiones:** los segmentos con mayor consumo representan oportunidades comerciales *potenciales*. El proyecto no calcula ingresos, costos ni rentabilidad por cliente; por tanto, no afirma que un mayor uso implique mayor valor financiero.

## Recomendaciones

- Revisar la oferta y las estrategias de retención para clientes de uso medio.
- Evaluar paquetes o beneficios adicionales para usuarios de alto consumo.
- Explorar alternativas flexibles para clientes de bajo uso.
- Analizar las cancelaciones junto con los segmentos para estudiar oportunidades de retención.
- Fortalecer las validaciones de calidad de datos para futuros análisis.

## Cómo ejecutar el notebook

1. Descarga o clona este repositorio.
2. Abre el archivo `.ipynb` del proyecto en **JupyterLab**, **Jupyter Notebook** o **Google Colab**.
3. Asegúrate de tener disponibles los tres CSV originales.
4. Si trabajas fuera de TripleTen, cambia en las celdas de lectura las rutas `/datasets/plans.csv`, `/datasets/users_latam.csv` y `/datasets/usage.csv` por las ubicaciones correspondientes en tu entorno.
5. Instala, si es necesario, las dependencias de Python:

   ```bash
   pip install pandas numpy matplotlib seaborn notebook
   ```

6. Ejecuta las celdas del notebook en orden, desde la primera hasta el informe ejecutivo.
7. Revisa las tablas, visualizaciones y conclusiones generadas.

## Estructura de entrega

```text
repositorio/
├── README.md
└── archivo-del-proyecto.ipynb
```

El nombre `archivo-del-proyecto.ipynb` es ilustrativo: conserva el nombre real del notebook al subirlo.

## Nota final

Este análisis es exploratorio y está orientado a identificar patrones y oportunidades de negocio. Las decisiones definitivas sobre precios y rentabilidad requieren información financiera adicional.
