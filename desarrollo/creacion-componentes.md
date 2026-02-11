<h1 style="color: #2196F3;">🧱 Superprompt: Creación de Componentes</h1>

Este superprompt está enfocado en la creación de componentes de UI, utilizando el `prompt-maestro-desarrollo` como base. Sirve para solicitar componentes bien estructurados, reutilizables y, opcionalmente, que sigan una filosofía como Atomic Design.

> **Abrir este superprompt:**
> ```bash
> code superprompts/desarrollo/creacion-componentes.md
> ```

> **Copiar este superprompt:**
> - **macOS:** `pbcopy < superprompts/desarrollo/creacion-componentes.md`
> - **Linux:** `xclip -selection clipboard < superprompts/desarrollo/creacion-componentes.md`
> - **Windows:** `clip < superprompts/desarrollo/creacion-componentes.md`

---

## creacion-componentes

### Versión Markdown (HTML)

Actúa como un <span style="color: #4CAF50;">**Desarrollador de Software Experto**</span>, especializado en desarrollo Frontend y sistemas de diseño.

**[CONTEXTO]**
- **Framework/Librería:** <span style="color: #FF9800;">`{{framework}}`</span> (Ej: "React con TypeScript", "Vue 3 con Composition API", "Svelte", "Angular 14").
- **Styling:** <span style="color: #FF9800;">`{{styling}}`</span> (Ej: "Styled-components", "TailwindCSS", "CSS Modules", "SASS").
- **Sistema de Diseño (opcional):** <span style="color: #FF9800;">`{{sistema_diseno}}`</span> (Ej: "Atomic Design", "Material Design").

**[TAREA]**
Necesito crear un componente de UI reutilizable.
- **Nombre del Componente:** <span style="color: #FF9800;">`{{nombre_componente}}`</span> (Ej: "Button", "Modal", "DataGrid", "DatePicker").
- **(Si aplica Atomic Design) Nivel:** <span style="color: #FF9800;">`{{nivel_atomico}}`</span> (Ej: "Átomo", "Molécula", "Organismo").
- **Props (Propiedades):** Define las propiedades que el componente debe aceptar.
    - <span style="color: #FF9800;">`{{prop_1}}`</span>: <span style="color: #FF9800;">`{{descripcion_prop_1}}`</span> (Ej: `variant`: "primary", "secondary" o "danger").
    - <span style="color: #FF9800;">`{{prop_2}}`</span>: <span style="color: #FF9800;">`{{descripcion_prop_2}}`</span> (Ej: `onClick`: "función a ejecutar al hacer clic").
    - <span style="color: #FF9800;">`{{prop_3}}`</span>: <span style="color: #FF9800;">`{{descripcion_prop_3}}`</span> (Ej: `isDisabled`: "booleano para deshabilitar").
- **Funcionalidad:** <span style="color: #FF9800;">`{{funcionalidad}}`</span> (Ej: "Debe mostrar un spinner cuando la prop `isLoading` sea true", "Debe cerrarse al presionar la tecla Escape").

**[FORMATO DE SALIDA]**
1.  **Estructura de Archivos:** El árbol de directorios para el componente (ej: `/Button/index.ts`, `/Button/Button.tsx`, `/Button/Button.styles.ts`).
2.  **Código del Componente:** El código completo del componente, siguiendo las mejores prácticas del framework (incluyendo tipos si es TypeScript).
3.  **Código de Estilos:** El código para los estilos del componente.
4.  **Ejemplo de Uso (y Storybook si aplica):** Cómo importar y usar el componente en otro lugar. Si se usa Storybook, proporciona el archivo de la historia (`Component.stories.tsx`).

**[RESTRICCIONES]**
- El componente debe ser completamente personalizable a través de sus props.
- Debe ser accesible (A11y), incluyendo roles ARIA y manejo del foco si es necesario.
- <span style="color: #FF9800;">`{{cualquier_otra_restriccion}}`</span>

---

### Versión para Terminal (ANSI)

```ansi
[1;32mActúa como un Desarrollador de Software Experto, especializado en Frontend y sistemas de diseño.[0m

[1m[CONTEXTO][0m
- [1mFramework/Librería:[0m [1;33m`{{framework}}`[0m (Ej: "React con TypeScript").
- [1mStyling:[0m [1;33m`{{styling}}`[0m (Ej: "TailwindCSS").
- [1mSistema de Diseño (opcional):[0m [1;33m`{{sistema_diseno}}`[0m (Ej: "Atomic Design").

[1m[TAREA][0m
Necesito crear un componente de UI reutilizable.
- [1mNombre del Componente:[0m [1;33m`{{nombre_componente}}`[0m (Ej: "Modal").
- [1m(Si aplica Atomic Design) Nivel:[0m [1;33m`{{nivel_atomico}}`[0m (Ej: "Organismo").
- [1mProps (Propiedades):[0m
    - [1;33m`{{prop_1}}`[0m: [1;33m`{{descripcion_prop_1}}`[0m
    - [1;33m`{{prop_2}}`[0m: [1;33m`{{descripcion_prop_2}}`[0m
- [1mFuncionalidad:[0m [1;33m`{{funcionalidad}}`[0m

[1m[FORMATO DE SALIDA][0m
1.  [1mEstructura de Archivos.[0m
2.  [1mCódigo del Componente.[0m
3.  [1mCódigo de Estilos.[0m
4.  [1mEjemplo de Uso / Storybook.[0m

[1m[RESTRICCIONES][0m
- Debe ser accesible (A11y).
- [1;33m`{{cualquier_otra_restriccion}}`[0m
```

---

## ⚡ Funciones rápidas para este proyecto

### Alias para usar este prompt
```bash
# alias sp-component="pbcopy < ~/superprompts/desarrollo/creacion-componentes.md && echo 'Copiado: Prompt Creación de Componentes'"
# Para Linux
# alias sp-component="xclip -selection clipboard < ~/superprompts/desarrollo/creacion-componentes.md && echo 'Copiado: Prompt Creación de Componentes'"
```

### Crear la estructura de un nuevo componente
```bash
function new-component() {
  if [ -z "$1" ] || [ -z "$2" ]; then
    echo "Uso: new-component NombreComponente extension (jsx, tsx, vue, etc.)"
    return 1
  fi
  
  COMP_NAME=$1
  EXT=$2
  # Puedes adaptar esta ruta según tu estructura
  DIR_PATH="src/components/$COMP_NAME"
  mkdir -p "$DIR_PATH"

  touch "$DIR_PATH/${COMP_NAME}.${EXT}"
  touch "$DIR_PATH/${COMP_NAME}.css"
  touch "$DIR_PATH/index.ts" # Para exportaciones

  echo "export * from './${COMP_NAME}';" > "$DIR_PATH/index.ts"
  
  echo "Estructura para el componente $COMP_NAME creada en $DIR_PATH"
  # code "$DIR_PATH/${COMP_NAME}.${EXT}"
}
```
