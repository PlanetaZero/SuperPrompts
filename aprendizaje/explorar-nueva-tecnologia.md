# <span style="color:#00FF66">🔬 SUPERPROMPT: EXPLORAR NUEVA TECNOLOGÍA</span>

## 🧩 Descripción
Este superprompt te guía en el proceso de aprender una nueva tecnología (librería, framework, herramienta) de forma estructurada, con un enfoque en la aplicación práctica y la creación de notas reutilizables.

---

## <span style="color:#00E5FF">🧠 Instrucciones para la IA</span>
Actúa como un **Investigador y Desarrollador Principal (Principal R&D Engineer)**. Tu especialidad es evaluar nuevas tecnologías, entender sus conceptos clave y crear un plan de acción para dominarlas rápidamente.

**[TAREA]**
Crea un plan de aprendizaje y un resumen técnico para la siguiente tecnología.

**1. TECNOLOGÍA A EXPLORAR:**
> {{nombre_de_la_tecnologia}}
> (Ej: "Zustand (State Management para React)", "htmx", "Temporal (Workflow Engine)")

**2. OBJETIVO FINAL:**
> {{objetivo_de_aprendizaje}}
> (Ej: "Evaluar si puede reemplazar a Redux en nuestro proyecto actual", "Entender cómo funciona para crear una demo interna", "Aprender sus conceptos básicos para una entrevista técnica").

**3. NIVEL DE PROFUNDIDAD:**
> {{nivel_de_profundidad}}
> (Ej: "Visión general (1 hora)", "Inmersión media (1 día)", "Dominio profundo (1 semana)")

**[FORMATO DE SALIDA]**
Quiero un plan de estudio y un resumen técnico en Markdown.
1.  **Resumen "Elevator Pitch":** ¿Qué es esta tecnología y qué problema principal resuelve? (en menos de 50 palabras).
2.  **Conceptos Clave:** Una lista de los 3-5 conceptos fundamentales que necesito entender para "captar" la esencia de la tecnología.
3.  **Pros y Contras:** ¿Cuáles son sus mayores ventajas y desventajas en comparación con sus alternativas?
4.  **Plan de Aprendizaje Práctico:** Un plan paso a paso según el nivel de profundidad solicitado.
    - **Paso 1 (Concepto):** Leer la documentación oficial sobre `X`.
    - **Paso 2 (Práctica):** Crear un "Hello World" o un mini-proyecto que implemente el concepto `X`.
    - **Paso 3 (Avanzado):** Intentar replicar una funcionalidad de mi proyecto actual usando esta tecnología.
5.  **Recursos Recomendados:** Enlaces a la documentación oficial, tutoriales clave (video o texto), y repositorios de ejemplo.
6.  **"Cheatsheet" de Código:** Un pequeño bloque de código con los snippets más comunes para empezar a usarla.

---

## <span style="color:#FFEB3B">🟦 Versión Terminal (ANSI)</span>
```bash
echo -e "
\e[32m🔬 SUPERPROMPT: EXPLORAR NUEVA TECNOLOGÍA\e[0m

\e[36m### INSTRUCCIONES PARA LA IA \e[0m
Actúa como un Investigador y Desarrollador Principal. Crea un plan de aprendizaje para la siguiente tecnología.

\e[33m[TECNOLOGÍA A EXPLORAR:]\e[0m
(Ej: \"Zustand (State Management para React)\")

\e[33m[OBJETIVO FINAL:]\e[0m
(Ej: \"Evaluar si puede reemplazar a Redux en nuestro proyecto\")

\e[33m[NIVEL DE PROFUNDIDAD:]\e[0m
(Ej: \"Inmersión media (1 día)\")

Tu respuesta debe ser un plan de estudio que incluya: Elevator Pitch, Conceptos Clave, Pros y Contras, Plan Práctico, Recursos y un Cheatsheet de código.
"
```

---

## 🟣 Comandos rápidos (modo app)
**Abrir este archivo:**
```bash
code superprompts/aprendizaje/explorar-nueva-tecnologia.md
```

**Copiar este superprompt:**
- **macOS:** `pbcopy < superprompts/aprendizaje/explorar-nueva-tecnologia.md`
- **Linux:** `xclip -selection clipboard < superprompts/aprendizaje/explorar-nueva-tecnologia.md`

---

## 🛠️ Funciones rápidas
```bash
# Función para crear un nuevo archivo de notas de aprendizaje
function learn() {
  if [ -z "$1" ]; then
    echo "Uso: learn nombre-de-la-tecnologia"
    return 1
  fi
  
  TECH_NAME_SLUG=$(echo "$1" | iconv -t ascii//TRANSLIT | sed -r 's/[^a-zA-Z0-9]+/-/g' | tr '[:upper:]' '[:lower:]')
  NOTES_DIR="docs/learning"
  mkdir -p "$NOTES_DIR"
  
  FILE_PATH="${NOTES_DIR}/${TECH_NAME_SLUG}.md"
  touch "$FILE_PATH"

  (cat ~/superprompts/aprendizaje/explorar-nueva-tecnologia.md) | pbcopy # o xclip

  echo "Archivo de notas creado en: $FILE_PATH"
  echo "El prompt para explorar la tecnología ha sido copiado al portapapeles."
  echo "Pégalo en la IA, rellénalo y guarda la respuesta en el archivo creado."
  # code "$FILE_PATH"
}
```

---

## 🗂️ Notas adicionales
- El aprendizaje activo (construir algo pequeño) es más efectivo que la lectura pasiva. Este prompt está diseñado para fomentar ese enfoque.
- Guarda las respuestas de la IA en una carpeta `docs/learning` para crear tu propia base de conocimiento.
