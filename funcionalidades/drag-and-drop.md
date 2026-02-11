<h1 style="color: #4DD0E1;">🖐️ Superprompt: Funcionalidad de Drag and Drop</h1>

Este superprompt solicita la implementación de una funcionalidad de arrastrar y soltar (Drag and Drop), por ejemplo, para reordenar una lista o mover elementos entre contenedores.

> **Abrir este superprompt:**
> ```bash
> code superprompts/funcionalidades/drag-and-drop.md
> ```

> **Copiar este superprompt:**
> - **macOS:** `pbcopy < superprompts/funcionalidades/drag-and-drop.md`
> - **Linux:** `xclip -selection clipboard < superprompts/funcionalidades/drag-and-drop.md`
> - **Windows:** `clip < superprompts/funcionalidades/drag-and-drop.md`

---

## drag-and-drop

### Versión Markdown (HTML)

Actúa como un <span style="color: #4CAF50;">**Desarrollador Frontend Experto**</span>, especializado en interacciones de usuario complejas y animaciones.

**[CONTEXTO]**
- **Framework:** <span style="color: #FF9800;">`{{framework}}`</span> (Ej: "React", "Vue", "Svelte").
- **Caso de Uso:** ¿Qué se necesita arrastrar y soltar?
  <span style="color: #FF9800;">`{{caso_de_uso}}`</span> (Ej: "Reordenar elementos en una única lista vertical", "Mover tarjetas entre varias columnas (estilo Trello/Kanban)", "Arrastrar un archivo desde el escritorio para subirlo").
- **Librería Preferida (opcional):** <span style="color: #FF9800;">`{{libreria}}`</span> (Ej: "dnd-kit", "react-beautiful-dnd", "SortableJS"). Si no se especifica, recomienda la más adecuada para el caso de uso y framework.

**[DATOS DE EJEMPLO]**
Proporciona la estructura de datos que se va a manipular.
```javascript
// Para una lista
const initialItems = [
  { id: 'item-1', content: 'Primer elemento' },
  { id: 'item-2', content: 'Segundo elemento' },
  { id: 'item-3', content: 'Tercer elemento' },
];

// Para columnas (Kanban)
const initialColumns = {
  'columna-1': {
    name: 'Por hacer',
    items: [ { id: 'task-1', content: 'Tarea 1' } ],
  },
  'columna-2': {
    name: 'En progreso',
    items: [],
  },
};
```

**[FORMATO DE SALIDA]**
1.  **Recomendación de Librería:** Justifica por qué la librería elegida es la mejor opción (mantenimiento, accesibilidad, rendimiento, etc.).
2.  **Instalación y Configuración:** Comandos para instalar la librería y cómo configurarla (ej: envolver la app en un `DndContext`).
3.  **Implementación de Componentes:**
    - **Contenedor(es):** El código del componente que actúa como área para soltar (`Droppable`).
    - **Elemento Arrastrable:** El código del componente que se puede arrastrar (`Draggable`).
4.  **Lógica de Estado:** Muestra la función que actualiza el estado (el orden de la lista o el contenido de las columnas) cuando el usuario suelta un elemento.
5.  **Estilos y Feedback Visual:** Proporciona CSS para indicar visualmente que un elemento se está arrastrando (ej: cambio de color de fondo, sombra) y que un contenedor es un destino válido.
6.  **Accesibilidad:** Menciona cómo asegurar que la funcionalidad sea accesible (ej: mediante sensores de teclado que permitan reordenar con las flechas).

---

### Versión para Terminal (ANSI)

```ansi
[1;32mActúa como un Desarrollador Frontend Experto, especializado en interacciones de usuario complejas.[0m

[1m[CONTEXTO][0m
- [1mFramework:[0m [1;33m`{{framework}}`[0m (Ej: "React").
- [1mCaso de Uso:[0m [1;33m`{{caso_de_uso}}`[0m (Ej: "Mover tarjetas entre varias columnas estilo Kanban").
- [1mLibrería Preferida (opcional):[0m [1;33m`{{libreria}}`[0m (Ej: "dnd-kit").

[1m[DATOS DE EJEMPLO][0m
[1;33m```javascript
// Proporciona aquí la estructura de datos a manipular.
```[0m

[1m[FORMATO DE SALIDA][0m
1.  [1mRecomendación de Librería:[0m Justificación de la elección.
2.  [1mInstalación y Configuración.[0m
3.  [1mImplementación de Componentes:[0m Código para `Droppable` y `Draggable`.
4.  [1mLógica de Estado:[0m La función que actualiza el estado al soltar.
5.  [1mEstilos y Feedback Visual:[0m CSS para el estado de arrastre.
6.  [1mAccesibilidad:[0m Cómo hacerlo accesible (ej: navegación por teclado).
```

---

## ⚡ Funciones rápidas para este proyecto

### Alias para usar este prompt
```bash
# alias sp-dnd="pbcopy < ~/superprompts/funcionalidades/drag-and-drop.md && echo 'Copiado: Prompt Drag and Drop'"
# Para Linux
# alias sp-dnd="xclip -selection clipboard < ~/superprompts/funcionalidades/drag-and-drop.md && echo 'Copiado: Prompt Drag and Drop'"
```

### Instalar dnd-kit (excelente librería para React)
```bash
function install-dnd-kit() {
    if [ -f "package.json" ]; then
        # Verificar si se está usando React
        if grep -q '"react"' package.json; then
            npm install @dnd-kit/core @dnd-kit/sortable
            echo "@dnd-kit instalado."
        else
            echo "Este instalador es para proyectos de React. Considera usar SortableJS para otros frameworks."
        fi
    else
        echo "No se encontró package.json."
    fi
}
```
