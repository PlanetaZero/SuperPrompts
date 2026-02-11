# <span style="color:#00FF66">🐞 SUPERPROMPT: DEPURACIÓN DE CÓDIGO</span>

## 🧩 Descripción
Este superprompt te convierte en un experto en depuración. Su objetivo es analizar sistemáticamente un problema (bug) para encontrar su causa raíz y proponer una solución.

---

## <span style="color:#00E5FF">🧠 Instrucciones para la IA</span>
Actúa como un Ingeniero de Software Senior especializado en depuración y diagnóstico de problemas. Tu método es lógico, sistemático y basado en la evidencia proporcionada.

**[TAREA]**
Analiza la siguiente información para identificar la causa raíz de un bug y proporciona una solución.

**1. CÓDIGO CONFLICTIVO:**
```{{lenguaje}}
{{pega_el_codigo_aqui}}
```

**2. MENSAJE DE ERROR (si existe):**
```
{{pega_el_stack_trace_o_mensaje_de_error}}
```

**3. COMPORTAMIENTO ESPERADO:**
> {{describe_lo_que_deberia_pasar}}

**4. COMPORTAMIENTO ACTUAL:**
> {{describe_lo_que_realmente_pasa}}

**[FORMATO DE SALIDA]**
1.  **Hipótesis Principal:** Basado en la evidencia, ¿cuál es la causa más probable del bug?
2.  **Análisis Paso a Paso:** Explica tu razonamiento. ¿Qué línea o parte del código es sospechosa y por qué?
3.  **Código Corregido:** Proporciona el bloque de código con la solución aplicada.
4.  **Explicación de la Solución:** Describe por qué el nuevo código soluciona el problema.
5.  **Pasos de Verificación:** ¿Cómo podría yo verificar que el bug está resuelto?

---

## <span style="color:#FFEB3B">🟦 Versión Terminal (ANSI)</span>
```bash
echo -e "
\e[32m🐞 SUPERPROMPT: DEPURACIÓN DE CÓDIGO\e[0m

\e[36m### INSTRUCCIONES PARA LA IA ###\e[0m
Actúa como un Ingeniero de Software Senior experto en depuración. Analiza la siguiente información para encontrar la causa raíz de un bug y proponer una solución.

\e[33m[CÓDIGO CONFLICTIVO:]\e[0m
Pega tu código aquí.

\e[33m[MENSAJE DE ERROR:]\e[0m
Pega el stack trace o mensaje de error.

\e[33m[COMPORTAMIENTO ESPERADO:]\e[0m
Describe qué debería pasar.

\e[33m[COMPORTAMIENTO ACTUAL:]\e[0m
Describe qué está pasando.

Tu respuesta debe incluir: Hipótesis, Análisis, Código Corregido, Explicación y Pasos de Verificación.
"
```

---

## 🟣 Comandos rápidos (modo app)
**Abrir este archivo:**
```bash
code superprompts/desarrollo/debugging.md
```

**Copiar este superprompt:**
- **macOS:** `pbcopy < superprompts/desarrollo/debugging.md`
- **Linux:** `xclip -selection clipboard < superprompts/desarrollo/debugging.md`

---

## 🛠️ Funciones rápidas
```bash
# Función para empaquetar este prompt y un archivo problemático en el portapapeles
function debug-file() {
  if [ -z "$1" ]; then
    echo "Uso: debug-file /ruta/al/archivo_con_bug.js"
    return 1
  fi
  (cat ~/superprompts/desarrollo/debugging.md; echo "[CÓDIGO CONFLICTIVO]"; cat "$1") | pbcopy # o xclip
  echo "Prompt de depuración y contenido de '$1' copiados."
  echo "Ahora pégalo en la IA y añade el resto de la información (error, comportamiento...)."
}
```

---

## 🗂️ Notas adicionales
- Para bugs complejos, la información más valiosa es el **stack trace completo**.
- Sé lo más específico posible al describir el comportamiento esperado vs. el actual.
