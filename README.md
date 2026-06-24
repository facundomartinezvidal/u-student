# u-student

Claude Code plugin para estudiantes universitarios y de cursos. Te ayuda a estudiar, resumir material, crear presentaciones, escribir trabajos prácticos y preparar exámenes — siempre en base al contenido de tu propia materia.

## ¿Para qué sirve?

- Resumir el material de cada clase según tu cronograma
- Crear presentaciones HTML exportables a PDF
- Escribir TPs e informes sección por sección
- Estudiar con flashcards, quizzes y simulacros de parcial
- Armar un plan de estudio personalizado
- Practicar la defensa oral de trabajos
- Organizar todos los archivos de la materia automáticamente

Todo responde en español y prioriza siempre tu propio material de cátedra.

## Instalación

Requiere [Claude Code](https://claude.ai/code).

```bash
claude plugin install u-student@fmartinezvidal-plugins --scope user
```

> Si no tenés el marketplace agregado:
> ```bash
> claude plugin marketplace add facundomartinezvidal/claude-plugins
> claude plugin install u-student@fmartinezvidal-plugins --scope user
> ```

## Primeros pasos

Abrí Claude Code en la carpeta de tu materia y corré:

```
/u-student:init
```

Esto crea la estructura de carpetas, el cronograma y un archivo `CLAUDE.md` que se carga automáticamente en cada sesión para que Claude sepa de qué materia se trata.

## Estructura de la materia

```
mi-materia/
├── CLAUDE.md                    # Contexto de la materia (generado por init)
├── cronograma.md                # Clases con temas, fechas y archivos
├── programa.md                  # Programa oficial de la cátedra
└── content/
    ├── primer-parcial/
    │   ├── 01-introduccion.pdf
    │   └── 02-tema-dos.md
    └── segundo-parcial/
        └── 03-tema-tres.pdf
```

Nombrar archivos como `NN-nombre-del-tema.ext` permite que el plugin los asocie automáticamente a cada clase del cronograma.

## Comandos

| Comando | Descripción |
|---------|-------------|
| `/u-student:init` | Inicializa el workspace de la materia |
| `/u-student:organize` | Organiza archivos sueltos en la estructura estándar |
| `/u-student:summarize` | Resume el material con cobertura del cronograma |
| `/u-student:study` | Sesión guiada para entender un concepto o problema |
| `/u-student:quiz` | Preguntas sin respuesta visible — feedback al responder |
| `/u-student:flashcards` | Flashcards con puntaje |
| `/u-student:exam` | Simulacro de parcial completo con corrección |
| `/u-student:explain` | Técnica Feynman — vos explicás, Claude da feedback |
| `/u-student:mindmap` | Mapa mental de los conceptos de la materia |
| `/u-student:compare` | Tabla comparativa entre conceptos |
| `/u-student:presentation` | Presentación HTML con notas del orador |
| `/u-student:defense` | Plan de defensa oral o simulación slide a slide |
| `/u-student:write` | Redacta TPs e informes sección por sección |
| `/u-student:export` | Exporta .html, .md o .docx a PDF |

## Agentes

Se activan automáticamente según lo que escribís:

| Agente | Se activa cuando decís... |
|--------|--------------------------|
| `tutor` | "no entiendo", "explicame", "qué es X" |
| `study-planner` | "tengo el parcial en X días", "armame un plan" |
| `tp-reviewer` | "revisá mi TP", "corregí el trabajo" |
| `writing-coach` | "cómo empiezo a redactar", "suena bien esto?" |
| `research-assistant` | "dónde busco fuentes", "esta fuente sirve?" |
| `exam-analyst` | "tengo parciales viejos", "qué toman siempre" |
| `progress-tracker` | "cuánto me falta", "cómo voy con la materia" |

## Flujo recomendado

```bash
# 1. Inicializar la materia
/u-student:init

# 2. Agregar material a content/primer-parcial/ y content/segundo-parcial/
#    Formato: 01-nombre-del-tema.pdf

# 3. Organizar archivos sueltos
/u-student:organize

# 4. Estudiar
/u-student:summarize
/u-student:quiz --parcial 1
/u-student:exam --parcial 1

# 5. Crear entregables
/u-student:presentation
/u-student:write
/u-student:export presentacion.html
```

## Requisitos

- [Claude Code](https://claude.ai/code) instalado
- No se requiere Git (el plugin lo detecta automáticamente)
- Para exportar a PDF: Chrome, pandoc o wkhtmltopdf (opcional — el plugin da instrucciones si falta alguno)

## Licencia

MIT
