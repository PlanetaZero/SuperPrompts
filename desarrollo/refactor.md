<h1 style="color: #2196F3;">🔧 Superprompt: Refactorizar Código</h1>

Este es un prompt específico para solicitar la refactorización de un fragmento de código. Utiliza el `prompt-maestro-limpieza` como base, pero se enfoca en un objetivo de refactorización concreto.

> **Abrir este superprompt:**
> ```bash
> code superprompts/desarrollo/refactor.md
> ```

> **Copiar este superprompt:**
> - **macOS:** `pbcopy < superprompts/desarrollo/refactor.md`
> - **Linux:** `xclip -selection clipboard < superprompts/desarrollo/refactor.md`
> - **Windows:** `clip < superprompts/desarrollo/refactor.md`

---

## refactor (Ejemplo Relleno)

### Versión Markdown (HTML)

Actúa como un <span style="color: #00BCD4;">**Analizador Estático de Código y Experto en Refactorización**</span>. Tu tarea es recibir un bloque de código y devolver una versión mejorada, junto con una explicación clara de los cambios realizados.
Tus directivas son: <span style="color: #2196F3;">**Legibilidad, Simplicidad, Eficiencia y Mantenibilidad**</span> (principios SOLID, DRY, KISS).

**[OBJETIVO DE REFACTORIZACIÓN]**
<span style="color: #FF9800;">`Quiero refactorizar esta función para que sea más legible y siga el Principio de Responsabilidad Única (SRP). Actualmente, hace demasiadas cosas: obtiene los datos, los filtra y luego los formatea. Quiero separar esas responsabilidades.`</span>

**[CÓDIGO FUENTE]**
```javascript
// Este código obtiene usuarios y los prepara para una lista de display
function getUserList() {
  fetch('https://api.example.com/users')
    .then(response => response.json())
    .then(data => {
      // Filtra usuarios activos
      const activeUsers = data.users.filter(u => u.status === 'active' && u.age > 18);
      
      // Formatea los nombres
      const formattedUsers = activeUsers.map(user => {
        return {
          fullName: `${user.firstName} ${user.lastName}`,
          id: user.id
        };
      });

      // Renderiza los usuarios (simulado)
      console.log('Rendering users:', formattedUsers);
      // renderUsers(formattedUsers);
    })
    .catch(error => console.error('Error fetching users:', error));
}
```

**[CONTEXTO]**
<span style="color: #FF9800;">`Esta función se encuentra en un componente de React (aunque aquí se muestra simplificada) y se llama cuando el componente se monta. El objetivo es mostrar una lista de usuarios activos.`</span>

**[FORMATO DE SALIDA]**
Quiero la respuesta en un formato de "code review":
1.  **Análisis General:** Una evaluación de alto nivel de la calidad del código original.
2.  **Puntos de Mejora:** Una lista detallada de los cambios que propones, explicando el "porqué" de cada uno.
3.  **Código Refactorizado:** La versión final y mejorada del código, separando las responsabilidades como se ha solicitado.
4.  **Tabla Comparativa (Opcional):** Una tabla que muestre el "Antes" y el "Después".

**[RESTRICCIONES]**
- No alteres la funcionalidad final. El resultado debe ser el mismo.
- La solución debe usar `async/await` para mejorar la legibilidad de las promesas.

---

### Versión para Terminal (ANSI)

```ansi
[1;36mActúa como un Analizador Estático de Código y Experto en Refactorización.[0m
[1;34mTus directivas son: Legibilidad, Simplicidad, Eficiencia y Mantenibilidad (SOLID, DRY, KISS).[0m

[1m[OBJETIVO DE REFACTORIZACIÓN][0m
[1;33m`Quiero refactorizar esta función para que sea más legible y siga el Principio de Responsabilidad Única (SRP). Actualmente, hace demasiadas cosas: obtiene los datos, los filtra y luego los formatea. Quiero separar esas responsabilidades.`[0m

[1m[CÓDIGO FUENTE][0m
[1;33m```javascript
// Este código obtiene usuarios y los prepara para una lista de display
function getUserList() {
  fetch('https://api.example.com/users')
    .then(response => response.json())
    .then(data => {
      // Filtra usuarios activos
      const activeUsers = data.users.filter(u => u.status === 'active' && u.age > 18);
      
      // Formatea los nombres
      const formattedUsers = activeUsers.map(user => {
        return {
          fullName: `${user.firstName} ${user.lastName}`,
          id: user.id
        };
      });

      // Renderiza los usuarios (simulado)
      console.log('Rendering users:', formattedUsers);
      // renderUsers(formattedUsers);
    })
    .catch(error => console.error('Error fetching users:', error));
}
```[0m

[1m[CONTEXTO][0m
[1;33m`Esta función se encuentra en un componente de React y se llama cuando el componente se monta.`[0m

[1m[FORMATO DE SALIDA][0m
Quiero la respuesta en un formato de "code review":
1.  [1mAnálisis General.[0m
2.  [1mPuntos de Mejora[0m (explicando el porqué).
3.  [1mCódigo Refactorizado[0m (separando responsabilidades).
4.  [1mTabla Comparativa (Opcional).[0m

[1m[RESTRICCIONES][0m
- No alteres la funcionalidad final.
- La solución debe usar `async/await`.
```

---

## ⚡ Funciones rápidas para este proyecto

### Alias para usar este prompt
```bash
# alias sp-refactor="pbcopy < ~/superprompts/desarrollo/refactor.md && echo 'Copiado: Prompt Refactorizar Código'"
# Para Linux
# alias sp-refactor="xclip -selection clipboard < ~/superprompts/desarrollo/refactor.md && echo 'Copiado: Prompt Refactorizar Código'"
```

### Analizar y refactorizar un archivo
Combina el prompt de refactorización y el contenido del archivo en el portapapeles.

```bash
function refactor-file() {
  if [ -z "$1" ]; then
    echo "Uso: refactor-file /ruta/al/archivo.js"
    return 1
  fi

  FILE_PATH=$1
  
  # Detectar OS y usar el comando de copia adecuado
  COPY_CMD=""
  if command -v pbcopy &> /dev/null; then
    COPY_CMD="pbcopy"
  elif command -v xclip &> /dev/null; then
    COPY_CMD="xclip -selection clipboard"
  else
    echo "Comando de copia no encontrado."
    return 1
  fi

  (cat ~/superprompts/desarrollo/refactor.md; echo ""; echo "---"; echo "[CÓDIGO FUENTE]"; cat "$FILE_PATH") | $COPY_CMD
  
  echo "Prompt de refactorización y contenido de '$FILE_PATH' copiados al portapapeles."
  echo "Edita el prompt en la IA con tu objetivo específico de refactorización."
}
```
