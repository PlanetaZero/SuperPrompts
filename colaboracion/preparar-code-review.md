# <span style="color:#00FF66">🤝 SUPERPROMPT: PREPARAR CODE REVIEW</span>

## 🧩 Descripción
Este superprompt te ayuda a preparar una Pull Request (PR) o Merge Request (MR) para que sea revisada por tu equipo. El objetivo es crear una descripción de PR clara, concisa y completa que facilite una revisión rápida y efectiva.

---

## <span style="color:#00E5FF">🧠 Instrucciones para la IA</span>
Actúa como un **Líder Técnico** y **Developer Advocate**. Tu tarea es tomar la información de una rama de Git y transformarla en una descripción de Pull Request ejemplar.

**[TAREA]**
Genera una descripción de PR en formato Markdown a partir de la siguiente información.

**1. TÍTULO DE LA PR:**
> {{titulo_de_la_pr}}
> (Ej: "feat(auth): Implementar login con Google")

**2. TICKET ASOCIADO (si aplica):**
> {{enlace_al_ticket}}
> (Ej: "Closes JIRA-123")

**3. LISTA DE CAMBIOS (git diff --summary):**
```
{{pega_aqui_el_resumen_de_cambios_de_git}}
```

**4. EXPLICACIÓN DE LOS CAMBIOS:**
> {{explica_brevemente_que_hiciste_y_por_que}}
> (Ej: "He añadido un nuevo controlador para el callback de Google, he creado un servicio para validar el token y he modificado el frontend para añadir el botón de login.")

**[FORMATO DE SALIDA]**
1.  **Descripción del Problema:** ¿Qué problema soluciona esta PR?
2.  **Solución Propuesta:** ¿Cómo se ha implementado la solución? (A alto nivel).
3.  **Cambios Principales:** Una lista de los cambios más importantes (puedes inferirlo del `git diff`).
4.  **¿Cómo Probarlo Manualmente?:** Pasos claros para que un revisor pueda verificar la funcionalidad.
5.  **Capturas de Pantalla / GIFs (Placeholder):** Un placeholder para que yo añada imágenes que demuestren el cambio visual.
6.  **Checklist de Autorevisión:** Una lista de puntos que el autor de la PR debería haber comprobado.

---

## <span style="color:#FFEB3B">🟦 Versión Terminal (ANSI)</span>
```bash
echo -e "
\e[32m🤝 SUPERPROMPT: PREPARAR CODE REVIEW\e[0m

\e[36m### INSTRUCCIONES PARA LA IA ###\e[0m
Actúa como un Líder Técnico y genera una descripción de Pull Request ejemplar en Markdown.

\e[33m[TÍTULO DE LA PR:]\e[0m
(Ej: feat(auth): Implementar login con Google)

\e[33m[LISTA DE CAMBIOS (git diff --summary)]\e[0m
(Pega aquí el resumen de git)

\e[33m[EXPLICACIÓN DE LOS CAMBIOS:]\e[0m
(Explica brevemente qué hiciste)

Tu respuesta debe incluir: Descripción del Problema, Solución Propuesta, Cambios Principales, Cómo Probarlo, Placeholders para capturas y un Checklist.
"
```

---

## 🟣 Comandos rápidos (modo app)
**Abrir este archivo:**
```bash
code superprompts/colaboracion/preparar-code-review.md
```

**Copiar este superprompt:**
- **macOS:** `pbcopy < superprompts/colaboracion/preparar-code-review.md`
- **Linux:** `xclip -selection clipboard < superprompts/colaboracion/preparar-code-review.md`

---

## 🛠️ Funciones rápidas
```bash
# Función para obtener el diff y copiar el prompt
function prep-pr() {
  # Asegúrate de estar en la rama correcta y que la rama 'main' o 'develop' esté actualizada
  # El comando de diff puede variar, este es un ejemplo contra 'main'
  
  GIT_DIFF_SUMMARY=$(git diff main --summary)
  
  if [ -z "$GIT_DIFF_SUMMARY" ]; then
    echo "No hay cambios para comparar con la rama 'main'. Asegúrate de estar en tu rama de feature."
    return 1
  fi

  (cat ~/superprompts/colaboracion/preparar-code-review.md; echo "[LISTA DE CAMBIOS]"; echo "$GIT_DIFF_SUMMARY") | pbcopy # o xclip

  echo "Prompt para PR y resumen de cambios copiados al portapapeles."
  echo "Pega esto en la IA y completa los detalles."
}
```

---

## 🗂️ Notas adicionales
- Una buena descripción de PR acelera la revisión, reduce los errores y mejora la documentación histórica del proyecto.
- Acostúmbrate a usar `prep-pr` antes de crear cada Pull Request.
