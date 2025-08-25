# 📚✨ Tesis en LaTeX – Factores de Riesgo en el Neurodesarrollo Infantil 🎓  

[![Compile LaTeX Thesis](https://github.com/dxnst/tesis-latex/actions/workflows/latex-compile.yml/badge.svg)](https://github.com/dxnst/tesis-latex/actions/workflows/latex-compile.yml)

¡Bienvenido/a al repositorio de mi tesis de graduación! Este proyecto documenta y organiza toda la investigación sobre **factores de riesgo en el neurodesarrollo infantil**, abordando un tema crucial para la salud pública en Guatemala. Todo el trabajo está compilado utilizando **LaTeX** para garantizar un formato académico profesional y de alta calidad.

---

## 📝 Descripción del Proyecto

Mi tesis investiga los factores de riesgo asociados al **neurodesarrollo infantil en Quetzaltenango, Guatemala**, tomando en cuenta variables socioeconómicas, nutricionales y de acceso a servicios de salud. Este estudio busca identificar patrones de riesgo mediante el uso del **Cuestionario Edades y Etapas 3 (ASQ-3)** y aportar datos relevantes para futuras intervenciones en el desarrollo infantil temprano.

---

## 🤖 Compilación Automática

Este repositorio incluye **GitHub Actions** para compilar automáticamente el documento LaTeX:

- **Triggers**: Se ejecuta en cada push a `main` y en pull requests
- **Ambiente**: Ubuntu con TeX Live completo
- **Proceso**: Utiliza `pdflatex` y `biber` para compilación y bibliografía
- **Artefactos**: El PDF final se guarda como artefacto descargable por 30 días

### Ver compilaciones

Puedes ver el estado de las compilaciones y descargar el PDF generado en la [página de Actions](https://github.com/dxnst/tesis-latex/actions).

---

## 🚀 Cómo Compilar Localmente

Sigue estos pasos para compilar correctamente el documento final:

1. Asegúrate de tener instalado un compilador de **LaTeX** (por ejemplo, [TeX Live](https://www.tug.org/texlive/), [MacTeX](https://www.tug.org/mactex/) o [MikTeX](https://miktex.org/)).
2. Clona este repositorio en tu computadora:
   ```bash
   git clone https://github.com/dxnst/tesis-latex.git
   cd tesis-latex/primer-impresion
   ```

3. Usa el comando make para compilar el documento:
   ```bash
   make build
   ```
4. El archivo PDF final se generará como `mydocument.pdf`.
