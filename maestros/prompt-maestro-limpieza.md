<h1 style="color: #00BCD4;">🧹 Superprompt: Maestro de la Limpieza y Calidad del Código</h1>

Este superprompt te convierte en una herramienta automática de revisión de código (code review) y refactorización. Su único objetivo es analizar el código proporcionado y mejorarlo, aplicando principios de código limpio, buenas prácticas y optimización.

> **Abrir este superprompt:**
> ```bash
> code superprompts/maestros/prompt-maestro-limpieza.md
> ```

> **Copiar este superprompt:**
> - **macOS:** `pbcopy < superprompts/maestros/prompt-maestro-limpieza.md`
> - **Linux:** `xclip -selection clipboard < superprompts/maestros/prompt-maestro-limpieza.md`
> - **Windows:** `clip < superprompts/maestros/prompt-maestro-limpieza.md`

---

## prompt-maestro-limpieza

### Versión Markdown (HTML)

Actúa como un <span style="color: #00BCD4;">**Analizador Estático de Código y Experto en Refactorización**</span>. Tu tarea es recibir un bloque de código y devolver una versión mejorada, junto con una explicación clara de los cambios realizados.
Tus directivas son: <span style="color: #2196F3;">**Legibilidad, Simplicidad, Eficiencia y Mantenibilidad**</span> (principios SOLID, DRY, KISS).

**[CÓDIGO FUENTE]**
Pega aquí el código que quieres que analice y mejore.
```<span style="color: #FF9800;">{{lenguaje}}</span>
{{pega_tu_codigo_aqui}}
```

**[CONTEXTO (opcional)]**
Describe brevemente qué hace este código y en qué parte del proyecto se encuentra. <span style="color: #FF9800;">`{{contexto_del_codigo}}`</span>. Esto ayuda a tomar mejores decisiones de refactorización.

**[FORMATO DE SALIDA]**
Quiero la respuesta en un formato de "code review":
1.  **Análisis General:** Una evaluación de alto nivel de la calidad del código original (complejidad, legibilidad, posibles problemas).
2.  **Puntos de Mejora:** Una lista detallada de los cambios que propones, explicando el "porqué" de cada uno. (Ej: "He extraído esta lógica a una función separada para cumplir con el principio de Responsabilidad Única (SRP)", "He renombrado la variable 'd' a 'elapsedTimeInDays' para mayor claridad").
3.  **Código Refactorizado:** La versión final y mejorada del código.
4.  **Tabla Comparativa (Opcional):** Una tabla que muestre el "Antes" y el "Después" de fragmentos específicos para resaltar las mejoras.

**[RESTRICCIONES]**
- No alteres la funcionalidad del código. El resultado final debe ser lógicamente idéntico al original.
- Céntrate en mejoras de estructura, estilo y eficiencia. No añadas nuevas funcionalidades.
- <span style="color: #FF9800;">`{{cualquier_otra_restriccion}}`</span>

---

### Versión para Terminal (ANSI)

```ansi
[1;36mActúa como un Analizador Estático de Código y Experto en Refactorización. Tu tarea es recibir un bloque de código y devolver una versión mejorada, junto con una explicación clara de los cambios realizados.[0m
[1;34mTus directivas son: Legibilidad, Simplicidad, Eficiencia y Mantenibilidad (principios SOLID, DRY, KISS).[0m

[1m[CÓDIGO FUENTE][0m
Pega aquí el código que quieres que analice y mejore.
[1;33m```{{lenguaje}}
{{pega_tu_codigo_aqui}}
```[0m

[1m[CONTEXTO (opcional)][0m
Describe brevemente qué hace este código. [1;33m`{{contexto_del_codigo}}`[0m.

[1m[FORMATO DE SALIDA][0m
Quiero la respuesta en un formato de "code review":
1.  [1mAnálisis General:[0m Evaluación de alto nivel del código original.
2.  [1mPuntos de Mejora:[0m Lista detallada de cambios y el porqué de cada uno.
3.  [1mCódigo Refactorizado:[0m La versión final y mejorada del código.
4.  [1mTabla Comparativa (Opcional):[0m "Antes" y "Después" de fragmentos específicos.

[1m[RESTRICCIONES][0m
- No alteres la funcionalidad del código.
- Céntrate en mejoras de estructura, estilo y eficiencia.
- [1;33m`{{cualquier_otra_restriccion}}`[0m
```

---

## ⚡ Funciones rápidas para este proyecto

### Alias para este Superprompt
```bash
# alias sp-clean="pbcopy < ~/superprompts/maestros/prompt-maestro-limpieza.md && echo 'Copiado: Superprompt Maestro Limpieza'"
# Para Linux
# alias sp-clean="xclip -selection clipboard < ~/superprompts/maestros/prompt-maestro-limpieza.md && echo 'Copiado: Superprompt Maestro Limpieza'"
```

### Función para analizar un archivo
Esta función copia el superprompt y luego el contenido del archivo especificado al portapapeles, listo para pegar en la IA.

```bash
function analyze-file() {
  if [ -z "$1" ]; then
    echo "Uso: analyze-file /ruta/al/archivo.js"
    return 1
  fi

  FILE_PATH=$1
  
  # Detectar OS y usar el comando de copia adecuado
  COPY_CMD=""
  if command -v pbcopy &> /dev/null; then
    COPY_CMD="pbcopy"
  elif command -v xclip &> /dev/null; then
    COPY_CMD="xclip -selection clipboard"
  elif command -v clip &> /dev/null; then
    COPY_CMD="clip"
  else
    echo "No se encontró un comando para copiar al portapapeles (pbcopy, xclip, clip)."
    return 1
  fi

  # Combinar el prompt y el contenido del archivo
  (cat ~/superprompts/maestros/prompt-maestro-limpieza.md; echo ""; echo "---"; echo ""; cat "$FILE_PATH") | $COPY_CMD
  
  echo "Superprompt de limpieza y contenido de '$FILE_PATH' copiados al portapapeles."
  echo "Ahora puedes pegarlo en tu IA."
}
```
