# Tablero TRM

Página web que muestra la Tasa Representativa del Mercado (TRM) de Colombia, en pesos por dólar: el valor vigente hoy y la tendencia del último año. Los datos se consultan en vivo cada vez que se abre la página o se pulsa **Actualizar**.

## Qué muestra

- La TRM vigente hoy y su cambio frente a la TRM anterior.
- La TRM del día siguiente, cuando ya está publicada.
- El máximo, el mínimo y el promedio diario del último año, y el cambio en 12 meses.
- Un gráfico de la tendencia del último año, que muestra el detalle de cada fecha con el cursor o con las flechas del teclado.
- Una tabla desplegable con todos los valores del año.

## Cómo usarla

Descarga `index.html` y ábrelo en el navegador. No requiere instalación, servidor ni clave de API, pero sí conexión a internet para consultar los datos.

Para verla en línea, activa GitHub Pages en **Settings → Pages**, con la rama `main` y la carpeta `/ (root)`. La página quedará en <https://lispulga0529.github.io/TABLERO--TRM/>.

## Fuente de datos

[Conjunto `32sa-8pi3` de datos.gov.co](https://www.datos.gov.co/d/32sa-8pi3), mediante su API pública:

```text
https://www.datos.gov.co/resource/32sa-8pi3.json
```

## Cómo se calculan los valores

- **TRM de hoy:** es la fila vigente en la fecha actual de Bogotá, no la más reciente, porque la API puede traer ya el valor del día siguiente.
- **Fines de semana y festivos:** comparten un mismo valor, por eso algunas filas cubren varios días.
- **Promedio diario:** cada valor pesa según los días que estuvo vigente.
- **Cambio en 12 meses:** compara la TRM de hoy con el primer valor del periodo consultado.
