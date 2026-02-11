<h1 style="color: #4DD0E1;">🔎 Superprompt: Búsqueda Inteligente</h1>

Este superprompt está diseñado para solicitar la implementación de una funcionalidad de búsqueda avanzada, que puede incluir autocompletado, corrección de errores tipográficos (fuzzy search) y ranking de relevancia.

> **Abrir este superprompt:**
> ```bash
> code superprompts/funcionalidades/busqueda-inteligente.md
> ```

> **Copiar este superprompt:**
> - **macOS:** `pbcopy < superprompts/funcionalidades/busqueda-inteligente.md`
> - **Linux:** `xclip -selection clipboard < superprompts/funcionalidades/busqueda-inteligente.md`
> - **Windows:** `clip < superprompts/funcionalidades/busqueda-inteligente.md`

---

## busqueda-inteligente

### Versión Markdown (HTML)

Actúa como un <span style="color: #4CAF50;">**Desarrollador de Software Experto**</span>, con experiencia en motores de búsqueda y procesamiento de texto.

**[CONTEXTO]**
- **Entorno:** <span style="color: #FF9800;">`{{entorno}}`</span> (Ej: "Frontend (React)", "Backend (Node.js)").
- **Fuente de Datos:** ¿Dónde están los datos sobre los que se va a buscar?
  <span style="color: #FF9800;">`{{fuente_de_datos}}`</span> (Ej: "Un array de objetos en el estado del cliente", "Una colección de productos en una base de datos PostgreSQL", "Un índice de Elasticsearch").
- **Datos de Ejemplo:** Proporciona un ejemplo de la estructura de un objeto de datos.
  ```json
  {
    "id": 123,
    "title": "El Gran Libro de la Programación",
    "author": "Jane Doe",
    "description": "Un libro sobre algoritmos y estructuras de datos.",
    "tags": ["programacion", "educativo", "informatica"]
  }
  ```

**[REQUISITOS DE LA BÚSQUEDA]**
- **Campos de Búsqueda:** ¿En qué campos del objeto se debe buscar?
  <span style="color: #FF9800;">`{{campos_busqueda}}`</span> (Ej: "title", "author", "description", "tags").
- **Funcionalidades Deseadas:**
  - [x] <span style="color: #FF9800;">`Autocompletado en tiempo real (mientras el usuario escribe).`</span>
  - [x] <span style="color: #FF9800;">`Tolerancia a errores tipográficos (Fuzzy Search).`</span>
  - [ ] <span style="color: #FF9800;">`Ranking de relevancia (ej: una coincidencia en 'title' pesa más que en 'description').`</span>
- **Librería Preferida (opcional):** <span style="color: #FF9800;">`{{libreria}}`</span> (Ej: "Fuse.js", "Lunr.js", "Algolia", "Meilisearch"). Si no se especifica, sugiere la más adecuada.

**[FORMATO DE SALIDA]**
1.  **Recomendación de Librería/Enfoque:** Justifica la elección de la librería o la estrategia (ej: por qué Fuse.js es bueno para búsqueda en el cliente).
2.  **Implementación:**
    - **Backend:** Si se requiere indexación, muestra cómo preparar los datos. Muestra el endpoint de la API para la búsqueda.
    - **Frontend:** Muestra el componente de React/Vue/etc. con el input de búsqueda, cómo gestiona el estado y cómo llama a la lógica de búsqueda.
3.  **Código de la Lógica de Búsqueda:** El código que implementa la búsqueda, ya sea configurando la librería recomendada o escribiendo la lógica desde cero si es simple.
4.  **Ejemplo de Uso:** Cómo integrar el componente de búsqueda en una aplicación.

---

### Versión para Terminal (ANSI)

```ansi
[1;32mActúa como un Desarrollador de Software Experto, con experiencia en motores de búsqueda.[0m

[1m[CONTEXTO][0m
- [1mEntorno:[0m [1;33m`{{entorno}}`[0m (Ej: "Frontend (React)").
- [1mFuente de Datos:[0m [1;33m`{{fuente_de_datos}}`[0m (Ej: "Un array de objetos en el cliente").
- [1mDatos de Ejemplo:[0m
  [1;33m```json
  { "id": 123, "title": "El Gran Libro de la Programación", ... }
  ```[0m

[1m[REQUISITOS DE LA BÚSQUEDA][0m
- [1mCampos de Búsqueda:[0m [1;33m`{{campos_busqueda}}`[0m (Ej: "title", "author").
- [1mFuncionalidades Deseadas:[0m
  - [x] [1;33m`Autocompletado en tiempo real.`[0m
  - [x] [1;33m`Tolerancia a errores tipográficos.`[0m
- [1mLibrería Preferida (opcional):[0m [1;33m`{{libreria}}`[0m (Ej: "Fuse.js").

[1m[FORMATO DE SALIDA][0m
1.  [1mRecomendación de Librería/Enfoque.[0m
2.  [1mImplementación:[0m Código Backend (si aplica) y Frontend.
3.  [1mCódigo de la Lógica de Búsqueda.[0m
4.  [1mEjemplo de Uso.[0m
```

---

## ⚡ Funciones rápidas para este proyecto

### Alias para usar este prompt
```bash
# alias sp-search="pbcopy < ~/superprompts/funcionalidades/busqueda-inteligente.md && echo 'Copiado: Prompt Búsqueda Inteligente'"
# Para Linux
# alias sp-search="xclip -selection clipboard < ~/superprompts/funcionalidades/busqueda-inteligente.md && echo 'Copiado: Prompt Búsqueda Inteligente'"
```

### Instalar Fuse.js (una popular librería de fuzzy search para JS)
```bash
function install-fuse() {
    if [ -f "package.json" ]; then
        npm install fuse.js
        echo "Fuse.js instalado."
    else
        echo "No se encontró package.json. Asegúrate de estar en un proyecto de Node.js."
    fi
}
```
