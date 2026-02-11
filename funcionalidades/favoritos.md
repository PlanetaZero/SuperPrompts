<h1 style="color: #4DD0E1;">⭐ Superprompt: Funcionalidad de Favoritos/Guardar</h1>

Este superprompt solicita la implementación de un sistema para que los usuarios puedan marcar elementos como "favoritos" o "guardarlos para más tarde".

> **Abrir este superprompt:**
> ```bash
> code superprompts/funcionalidades/favoritos.md
> ```

> **Copiar este superprompt:**
> - **macOS:** `pbcopy < superprompts/funcionalidades/favoritos.md`
> - **Linux:** `xclip -selection clipboard < superprompts/funcionalidades/favoritos.md`
> - **Windows:** `clip < superprompts/funcionalidades/favoritos.md`

---

## favoritos

### Versión Markdown (HTML)

Actúa como un <span style="color: #4CAF50;">**Desarrollador Full-Stack Experto**</span>. Tu tarea es diseñar e implementar un sistema de "favoritos" de principio a fin.

**[CONTEXTO]**
- **Elemento a Guardar:** ¿Qué tipo de entidad pueden guardar los usuarios?
  <span style="color: #FF9800;">`{{entidad_a_guardar}}`</span> (Ej: "Productos", "Artículos de un blog", "Publicaciones en una red social", "Canciones").
- **Persistencia de Datos:** ¿Dónde se debe guardar el estado de los favoritos?
  <span style="color: #FF9800;">`{{persistencia_datos}}`</span> (Ej: "En la base de datos (requiere autenticación de usuario)", "En el `localStorage` del navegador (para usuarios no registrados)").
- **Stack Tecnológico:**
  - **Frontend:** <span style="color: #FF9800;">`{{stack_frontend}}`</span> (Ej: "React, Redux Toolkit")
  - **Backend:** <span style="color: #FF9800;">`{{stack_backend}}`</span> (Ej: "Node.js, Express, PostgreSQL")

**[FORMATO DE SALIDA]**
Quiero una implementación completa, dividida en frontend y backend.

**Parte 1: Backend**
1.  **Diseño de la Base de Datos:**
    - Muestra el SQL (DDL) para la nueva tabla de unión (ej: `user_favorite_products`) que relaciona usuarios y elementos. Debe incluir claves foráneas y un índice único para evitar duplicados.
2.  **API Endpoints:**
    - Diseña los endpoints RESTful necesarios:
      - `POST /api/items/{itemId}/favorite`: Para añadir un favorito.
      - `DELETE /api/items/{itemId}/favorite`: Para quitar un favorito.
      - `GET /api/me/favorites`: Para obtener todos los favoritos del usuario actual.
    - Muestra el código de los controladores y servicios que implementan esta lógica. Incluye la validación (ej: asegurar que el usuario esté autenticado y que el item exista).

**Parte 2: Frontend**
1.  **Gestión de Estado (State Management):**
    - Muestra cómo gestionar el estado de los favoritos en el cliente. Si usas una librería como Redux o Zustand, muestra el "slice" o "store" de favoritos.
    - Incluye las acciones para añadir, quitar y cargar los favoritos desde la API.
2.  **Componente de UI:**
    - El código para un botón de "Favorito" (`FavoriteButton.tsx`).
    - Este botón debe ser "optimista": cambiar su estado visual inmediatamente y luego sincronizarse con el backend. Debe manejar los casos de éxito y error.
3.  **Integración:**
    - Muestra cómo usar el `FavoriteButton` en una tarjeta de producto o artículo.
    - Muestra cómo crear una página de "Mis Favoritos" que obtenga los datos de la API y muestre la lista de elementos guardados.

---

### Versión para Terminal (ANSI)

```ansi
[1;32mActúa como un Desarrollador Full-Stack Experto. Tu tarea es diseñar un sistema de "favoritos".[0m

[1m[CONTEXTO][0m
- [1mElemento a Guardar:[0m [1;33m`{{entidad_a_guardar}}`[0m (Ej: "Productos").
- [1mPersistencia de Datos:[0m [1;33m`{{persistencia_datos}}`[0m (Ej: "En la base de datos").
- [1mStack Tecnológico:[0m
  - [1mFrontend:[0m [1;33m`{{stack_frontend}}`[0m
  - [1mBackend:[0m [1;33m`{{stack_backend}}`[0m

[1m[FORMATO DE SALIDA][0m
Quiero una implementación completa Full-Stack.

[1mParte 1: Backend[0m
1.  [1mDiseño de la Base de Datos:[0m SQL para la tabla de unión (ej: `user_favorites`).
2.  [1mAPI Endpoints:[0m Código para los endpoints `POST`, `DELETE`, y `GET` de favoritos.

[1mParte 2: Frontend[0m
1.  [1mGestión de Estado:[0m Código del "slice" de Redux/Zustand para favoritos.
2.  [1mComponente de UI:[0m Código para un `FavoriteButton.tsx` con UI optimista.
3.  [1mIntegración:[0m Cómo usar el botón y crear la página de "Mis Favoritos".
```

---

## ⚡ Funciones rápidas para este proyecto

### Alias para usar este prompt
```bash
# alias sp-favs="pbcopy < ~/superprompts/funcionalidades/favoritos.md && echo 'Copiado: Prompt Funcionalidad de Favoritos'"
# Para Linux
# alias sp-favs="xclip -selection clipboard < ~/superprompts/funcionalidades/favoritos.md && echo 'Copiado: Prompt Funcionalidad de Favoritos'"
```

### Crear una migración para la tabla de favoritos (ejemplo con Knex.js)
```bash
function new-favorites-migration() {
    if command -v npx &> /dev/null && [ -f "knexfile.js" ]; then
        npx knex migrate:make create_user_favorites_table
        echo "Migración creada. Edita el archivo para añadir las columnas:"
        echo "- user_id (foreign key a users.id)"
        echo "- item_id (foreign key a items.id)"
        echo "- created_at"
        echo "Añade un índice único en [user_id, item_id]."
    else
        echo "Comando 'npx' o archivo 'knexfile.js' no encontrado."
    fi
}
```
