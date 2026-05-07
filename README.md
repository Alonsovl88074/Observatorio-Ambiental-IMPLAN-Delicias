# Observatorio-Ambiental-IMPLAN-Delicias
Tablero técnico para monitorear desplazamientos, kilómetros recorridos, emisiones de CO2, intensidad modal y desempeño territorial del sistema de movilidad.

## Descripción
Este repositorio contiene un tablero web técnico orientado al análisis de movilidad urbana y sustentabilidad ambiental para Delicias, Chihuahua.

El observatorio presenta indicadores de desplazamientos, kilómetros recorridos, emisiones de CO2e, presión vial motorizada, movilidad activa, equilibrio territorial y comparativos analíticos por modo y sentido de desplazamiento.

La versión publicada en GitHub Pages fue ajustada para operar de forma estable con datos integrados dentro del propio archivo `index.html`, evitando fallas de lectura remota del CSV publicado de Google Sheets.

## Objetivo
El propósito del proyecto es facilitar la lectura ejecutiva y técnica de la movilidad urbana mediante visualizaciones claras, filtros interactivos y métricas que ayuden a la toma de decisiones de planeación, sustentabilidad y gestión territorial.

## Contenido del tablero
### Indicadores principales
- Total de desplazamientos.
- Kilómetros recorridos.
- Emisiones de CO2e.
- Índice de movilidad activa.
- CO2e por 1,000 viajes.
- Balance entrada / salida.
- Presión vial motorizada.

### Tarjetas analíticas
- Medios y combustibles.
- Dirección de los flujos.
- Volumen de desplazamientos.
- Eficiencia de emisiones.
- Accesibilidad urbana.
- Movilidad activa.
- Desacople ambiental.
- Equilibrio territorial.

### Visualizaciones
- Dona de sentido del desplazamiento.
- Barras apiladas de interacción entre modo, sentido y volumen.
- Línea de tiempo anual de emisiones y desplazamientos/kilómetros.
- Histograma por medio de transporte.
- Radar de sostenibilidad.
- Comparativo A/B de motorizados vs activos.
- Comparativo A/B de entrantes vs salientes.

## Fuente de datos
Los datos fueron integrados nativamente a partir de la base principal originalmente publicada en Google Sheets.

Columnas base utilizadas:
- `modo`
- `sentido del desplazamiento`
- `desplazamiento`
- `distancia total (km)`
- `toneladas de CO2e totales`
- `año`

Resumen de integración:
- Registros detectados en el CSV original: {summary.get('row_count_csv', 'N/D')}
- Registros integrados en el tablero: {summary.get('row_count_embedded', 'N/D')}
- Suma total de desplazamientos integrados: {summary.get('sum_trips', 'N/D')}

## Arquitectura técnica
El proyecto está construido como una página estática en HTML con apoyo de Tailwind CSS para estilos visuales y Chart.js para las gráficas.

La lógica del tablero está implementada en JavaScript del lado del cliente e incluye:
- carga local de datos integrados;
- normalización de texto y encabezados;
- filtros por año, modo y sentido;
- cálculo dinámico de KPIs;
- actualización coordinada de gráficas y tarjetas;
- ayudas contextuales mediante popovers con icono de foco.

## Estabilidad implementada
Esta versión corrige problemas previos de despliegue, especialmente en GitHub Pages:
- evita la dependencia del fetch remoto al CSV;
- evita confundir la columna `desplazamiento` con `sentido del desplazamiento`;
- prioriza campos de totales sobre variantes GPC;
- mantiene funcionamiento estable sin backend;
- reduce errores por codificación, caché o lectura parcial de la fuente externa.

## Publicación en GitHub Pages
### Requisitos
- Tener un repositorio público o con Pages habilitado.
- Colocar el archivo principal como `index.html` en la raíz del repositorio.

### Pasos
1. Subir `index.html` a la raíz del repositorio.
2. Ir a **Settings > Pages**.
3. En **Build and deployment**, seleccionar **Deploy from a branch**.
4. Elegir la rama principal (`main` o `master`) y la carpeta `/(root)`.
5. Guardar los cambios y esperar la publicación.

## Estructura sugerida del repositorio
```bash
.
├── index.html
├── README.md
└── assets/   # opcional, si después agregas logos, capturas o iconos externos
```

## Uso local
Puedes abrir el archivo `index.html` directamente en el navegador o servirlo desde un servidor local simple.

Ejemplo con Python:
```bash
python -m http.server 8000
```

Luego abre:
```bash
http://localhost:8000
```

## Personalización futura
Mejoras recomendadas para próximas versiones:
- separar datos, lógica y estilos en archivos independientes;
- agregar exportación a CSV o Excel desde el navegador;
- integrar versiones temáticas por sector o año;
- conectar nuevamente con Google Sheets mediante un proceso de actualización controlado;
- añadir metadatos institucionales, logotipo y créditos técnicos.

## Créditos
Desarrollo, integración y adaptación del observatorio para análisis urbano y ambiental orientado a IMPLAN Delicias.

## Licencia
Define aquí la licencia que quieras usar para el proyecto, por ejemplo MIT, Apache-2.0 o una licencia institucional interna.
