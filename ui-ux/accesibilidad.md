<h1 style="color: #F44336;">♿ Superprompt: Auditoría de Accesibilidad (A11y)</h1>

Este superprompt está enfocado en analizar y mejorar la accesibilidad de una página web o componente de UI, identificando problemas y proponiendo soluciones concretas.

> **Abrir este superprompt:**
> ```bash
> code superprompts/ui-ux/accesibilidad.md
> ```

> **Copiar este superprompt:**
> - **macOS:** `pbcopy < superprompts/ui-ux/accesibilidad.md`
> - **Linux:** `xclip -selection clipboard < superprompts/ui-ux/accesibilidad.md`
> - **Windows:** `clip < superprompts/ui-ux/accesibilidad.md`

---

## accesibilidad

### Versión Markdown (HTML)

Actúa como un <span style="color: #E91E63;">**Especialista en Accesibilidad Web (A11y)**</span>. Tu misión es auditar el código HTML/JSX proporcionado para asegurar que cumple con los estándares de la <span style="color: #2196F3;">**WCAG 2.1 (Web Content Accessibility Guidelines)**</span>, al menos a nivel AA.

**[CÓDIGO A AUDITAR]**
Pega aquí el código HTML, JSX, Vue, etc., del componente o página que quieres analizar.
```html
<div class="profile-card">
    <img src="user.jpg">
    <h3>John Doe</h3>
    <p>Software Developer</p>
    <div onclick="showMoreInfo()">Ver más</div>
</div>
```

**[CONTEXTO DE USO]**
Describe brevemente dónde y cómo se usa este componente.
<span style="color: #FF9800;">`{{contexto_de_uso}}`</span>
(Ej: "Es una tarjeta de perfil de usuario que se muestra en una lista. Al hacer clic en 'Ver más', se debería expandir para mostrar más detalles. Es interactuable.").

**[FORMATO DE SALIDA]**
Quiero un informe de auditoría y una solución mejorada:
1.  **Informe de Auditoría de Accesibilidad:**
    - Una lista de los problemas de accesibilidad encontrados en el código original.
    - Para cada problema, explica:
        - **Problema:** ¿Cuál es el error? (Ej: "La imagen no tiene texto alternativo").
        - **Impacto:** ¿A qué usuarios afecta y cómo? (Ej: "Los usuarios con lectores de pantalla no sabrán qué muestra la imagen").
        - **Referencia WCAG:** El criterio de la WCAG que se está incumpliendo (Ej: "1.1.1 Contenido no textual").
2.  **Código Corregido:**
    - La versión mejorada del código, con todos los problemas de accesibilidad solucionados.
3.  **Explicación de los Cambios:**
    - Detalla qué cambios has hecho y por qué mejoran la accesibilidad. (Ej: "Añadí el atributo `alt` a la imagen...", "Cambié el `div` con `onclick` por un elemento `<button>` para que sea enfocable por teclado y los lectores de pantalla lo anuncien como un control interactivo", "Añadí `aria-expanded` para comunicar el estado del contenido expandible").
4.  **Recomendaciones Adicionales:**
    - Sugerencias para probar la accesibilidad manualmente (ej: "Intenta navegar por el componente usando solo el tabulador", "Usa un lector de pantalla como NVDA o VoiceOver").

---

### Versión para Terminal (ANSI)

```ansi
[1;35mActúa como un Especialista en Accesibilidad Web (A11y). Tu misión es auditar el código para que cumpla con la WCAG 2.1 a nivel AA.[0m

[1m[CÓDIGO A AUDITAR][0m
[1;33m```html
<div class="profile-card">
    <img src="user.jpg">
    <h3>John Doe</h3>
    <p>Software Developer</p>
    <div onclick="showMoreInfo()">Ver más</div>
</div>
```[0m

[1m[CONTEXTO DE USO][0m
Describe brevemente dónde y cómo se usa este componente.
[1;33m`{{contexto_de_uso}}`[0m

[1m[FORMATO DE SALIDA][0m
Quiero un informe de auditoría y una solución:
1.  [1mInforme de Auditoría de Accesibilidad:[0m
    - Lista de problemas encontrados.
    - Para cada uno: Problema, Impacto y Referencia WCAG.
2.  [1mCódigo Corregido:[0m La versión mejorada del código.
3.  [1mExplicación de los Cambios:[0m Detalla qué has cambiado y por qué.
4.  [1mRecomendaciones Adicionales:[0m Sugerencias para probar manualmente.
```

---

## ⚡ Funciones rápidas para este proyecto

### Alias para usar este prompt
```bash
# alias sp-a11y="pbcopy < ~/superprompts/ui-ux/accesibilidad.md && echo 'Copiado: Prompt Auditoría de Accesibilidad'"
# Para Linux
# alias sp-a11y="xclip -selection clipboard < ~/superprompts/ui-ux/accesibilidad.md && echo 'Copiado: Prompt Auditoría de Accesibilidad'"
```

### Auditar un archivo
Prepara el prompt y el contenido del archivo especificado para una rápida auditoría de accesibilidad.

```bash
function audit-a11y-file() {
  if [ -z "$1" ]; then
    echo "Uso: audit-a11y-file /ruta/al/componente.jsx"
    return 1
  fi

  FILE_PATH=$1
  
  COPY_CMD=""
  if command -v pbcopy &> /dev/null; then COPY_CMD="pbcopy";
  elif command -v xclip &> /dev/null; then COPY_CMD="xclip -selection clipboard";
  else echo "Comando de copia no encontrado." && return 1; fi

  (cat ~/superprompts/ui-ux/accesibilidad.md; echo ""; echo "---"; echo "[CÓDIGO A AUDITAR]"; cat "$FILE_PATH") | $COPY_CMD
  
  echo "Prompt de accesibilidad y contenido de '$FILE_PATH' copiados al portapapeles."
  echo "No olvides añadir el contexto de uso en la IA."
}
```
