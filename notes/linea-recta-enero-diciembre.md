# Línea recta de enero a diciembre

Objetivo: crear una serie lineal que vaya desde **998** hasta **4227** a lo largo de los 12 meses del año.

## Valores mensuales (lineales)

- ene: 998
- feb: 1292
- mar: 1585
- abr: 1879
- may: 2172
- jun: 2466
- jul: 2760
- ago: 3053
- sep: 3347
- oct: 3640
- nov: 3934
- dic: 4227

## Incremento mensual

La diferencia total es 4227 - 998 = 3229.

Como hay 11 saltos entre enero y diciembre, el incremento lineal es:

3229 / 11 = 293.5454545

## Fórmula DAX sugerida

```DAX
LineaRecta =
VAR MesNum = SELECTEDVALUE('DimCalendario'[MesNumero])
VAR Inicio = 998
VAR Fin = 4227
VAR Pasos = 11
RETURN
    Inicio + DIVIDE((Fin - Inicio) * (MesNum - 1), Pasos)
```

Si quieres valores enteros redondeados:

```DAX
LineaRectaRedondeada =
ROUND([LineaRecta], 0)
```
