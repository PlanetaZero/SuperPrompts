<h1 style="color: #673AB7;">📁 Superprompt: Estructura de Carpetas</h1>

Este superprompt solicita una estructura de carpetas detallada y justificada para un tipo de proyecto específico. Es ideal para estandarizar la organización del código desde el inicio.

> **Abrir este superprompt:**
> ```bash
> code superprompts/arquitectura/estructura-carpetas.md
> ```

> **Copiar este superprompt:**
> - **macOS:** `pbcopy < superprompts/arquitectura/estructura-carpetas.md`
> - **Linux:** `xclip -selection clipboard < superprompts/arquitectura/estructura-carpetas.md`
> - **Windows:** `clip < superprompts/arquitectura/estructura-carpetas.md`

---

## estructura-carpetas

### Versión Markdown (HTML)

Actúa como un <span style="color: #9C27B0;">**Arquitecto de Software Principal**</span> con especialización en organización de proyectos y código limpio.

**[CONTEXTO]**
Necesito la estructura de carpetas ideal para un proyecto con las siguientes características:
- **Tipo de Proyecto:** <span style="color: #FF9800;">`{{tipo_de_proyecto}}`</span> (Ej: "API RESTful con Node.js y Express", "Aplicación web Frontend con React", "Monorepo Full-Stack con Next.js y NestJS", "Librería de componentes UI").
- **Paradigma/Arquitectura:** <span style="color: #FF9800;">`{{paradigma_arquitectonico}}`</span> (Ej: "Arquitectura Hexagonal", "Orientado a funcionalidades (feature-based)", "Atomic Design", "Arquitectura por capas tradicional").
- **Stack Tecnológico Principal:** <span style="color: #FF9800;">`{{stack_tecnologico}}`</span> (Ej: "TypeScript, PostgreSQL, Docker, Prisma", "JavaScript, Jest, Storybook, Rollup").

**[FORMATO DE SALIDA]**
Quiero la respuesta en el siguiente formato:
1.  **Árbol de Directorios:** Una representación visual completa de la estructura de carpetas usando un formato de árbol.
2.  **Justificación Detallada:** Una tabla o lista que explique el propósito de cada carpeta y subcarpeta principal.
    - **Carpeta:** El nombre de la carpeta (ej: `/src/core/services`).
    - **Propósito:** La responsabilidad de esa carpeta (ej: "Contiene la lógica de negocio central, independiente del framework").
3.  **Archivos Clave:** Menciona algunos archivos importantes que irían dentro de ciertas carpetas y su función (ej: `index.ts` para exportaciones, `.env.example` para variables de entorno).

**[EJEMPLO DE USO]**
- **Tipo de Proyecto:** `API RESTful con Node.js y Express`
- **Paradigma/Arquitectura:** `Arquitectura por capas (Controllers, Services, Repositories)`
- **Stack Tecnológico Principal:** `TypeScript, PostgreSQL, Prisma, Jest`

---

### Versión para Terminal (ANSI)

```ansi
[1;35mActúa como un Arquitecto de Software Principal con especialización en organización de proyectos y código limpio.[0m

[1m[CONTEXTO][0m
Necesito la estructura de carpetas ideal para un proyecto con las siguientes características:
- [1mTipo de Proyecto:[0m [1;33m`{{tipo_de_proyecto}}`[0m (Ej: "API RESTful con Node.js y Express").
- [1mParadigma/Arquitectura:[0m [1;33m`{{paradigma_arquitectonico}}`[0m (Ej: "Arquitectura Hexagonal").
- [1mStack Tecnológico Principal:[0m [1;33m`{{stack_tecnologico}}`[0m (Ej: "TypeScript, PostgreSQL, Docker").

[1m[FORMATO DE SALIDA][0m
Quiero la respuesta en el siguiente formato:
1.  [1mÁrbol de Directorios:[0m Una representación visual completa de la estructura de carpetas.
2.  [1mJustificación Detallada:[0m Una tabla o lista que explique el propósito de cada carpeta principal.
3.  [1mArchivos Clave:[0m Menciona algunos archivos importantes y su función.

[1m[EJEMPLO DE USO][0m
- [1mTipo de Proyecto:[0m `API RESTful con Node.js y Express`
- [1mParadigma/Arquitectura:[0m `Arquitectura por capas (Controllers, Services, Repositories)`
- [1mStack Tecnológico Principal:[0m `TypeScript, PostgreSQL, Prisma, Jest`
```

---

## ⚡ Funciones rápidas para este proyecto

### Alias para usar este prompt
```bash
# alias sp-struct="pbcopy < ~/superprompts/arquitectura/estructura-carpetas.md && echo 'Copiado: Prompt Estructura de Carpetas'"
# Para Linux
# alias sp-struct="xclip -selection clipboard < ~/superprompts/arquitectura/estructura-carpetas.md && echo 'Copiado: Prompt Estructura de Carpetas'"
```

### Generar la estructura de carpetas en el disco
Esta función toma la salida del árbol de directorios (generada por la IA) y la crea en el sistema de archivos.

```bash
function scaffold-from-ia() {
    if [ -z "$1" ]; then
        echo "Uso: scaffold-from-ia /ruta/al/archivo_con_arbol.txt"
        echo "El archivo debe contener la estructura de árbol copiada de la IA."
        return 1
    fi

    INPUT_FILE=$1
    
    # Limpia la entrada para obtener solo las rutas de directorios
    # Este sed elimina prefijos de árbol, archivos y espacios en blanco
    cat "$INPUT_FILE" | sed -e 's/|-- //g' -e 's/`-- //g' -e 's/|   //g' -e 's/    //g' -e '/\./d' | while read -r line; do
        # Elimina caracteres extraños que a veces las IAs añaden
        clean_line=$(echo "$line" | tr -d '[:space:]' | sed 's/└─//g' | sed 's/├─//g')
        if [ -n "$clean_line" ]; then
            mkdir -p "$clean_line"
            echo "Creado: $clean_line"
        fi
    done

    echo "Estructura de carpetas generada."
}
# Para usarlo:
# 1. Pega la salida de la IA en un archivo, por ejemplo, `ia_tree.txt`.
# 2. Ejecuta `scaffold-from-ia ia_tree.txt`
```
