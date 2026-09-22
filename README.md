# Radioenlaces PtP – Actividad 2, Parte 1 (presentación Beamer)

## Estructura
```
main.tex                  # documento principal: solo \input de las partes
config/estilo.tex         # paquetes, colores, macros (\completar, \figura)
datos/enlace_A.tex        # NÚMEROS del Enlace A  -> edita el equipo A
datos/enlace_B.tex        # NÚMEROS del Enlace B  -> edita el equipo B
secciones/01_teoria.tex       # teoría común
secciones/02_enlace_A.tex     # diapositivas Enlace A -> equipo A
secciones/03_enlace_B.tex     # diapositivas Enlace B -> equipo B
secciones/04_comparacion.tex  # tabla A vs B (se llena sola desde datos/)
secciones/05_conclusiones.tex
figuras/                  # A_*.png|jpg y B_*.png|jpg
```

## Cómo completar
- Todo lo pendiente aparece en el PDF como **[COMPLETAR]** resaltado.
- Los valores numéricos se cambian **solo** en `datos/enlace_X.tex`; se actualizan en
  las diapositivas y en la tabla comparativa.
- Figuras faltantes aparecen como recuadro "FIGURA PENDIENTE" con el nombre esperado.

## Compilar
```
latexmk -pdf main.tex        # compila
latexmk -pvc -pdf main.tex   # recompila al guardar
latexmk -c                   # limpia auxiliares
```
En VS Code: extensión **LaTeX Workshop** (compila al guardar).

## Flujo de trabajo con git
Cada equipo trabaja en su rama y en sus archivos para evitar conflictos:
```
git pull
git checkout -b enlace-a          # o enlace-b
# ... editar ...
git add .
git commit -m "Enlace A: relevamiento y Fresnel"
git push -u origin enlace-a
```
Luego se abre un Pull Request hacia `main`.

## Parte 2 (carpeta `parte2/`)
Presentación separada que reutiliza el estilo común (`config/estilo.tex`).
```
cd parte2
latexmk -pdf main.tex
```
- `parte2/datos/grupos.tex`: qué grupo estuvo en cada extremo (AP / Station).
- `parte2/secciones/05_grupos.tex`: diferencias y resultados del otro extremo (a completar).
- Figuras propias en `parte2/figuras/`; las del otro grupo con prefijo `G2_`.
