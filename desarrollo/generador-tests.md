<h1 style="color: #2196F3;">🧪 Superprompt: Generador de Tests</h1>

Este superprompt se enfoca en la creación de tests (unitarios, de integración, E2E) para un fragmento de código o una funcionalidad existente, siguiendo las mejores prácticas de testing.

> **Abrir este superprompt:**
> ```bash
> code superprompts/desarrollo/generador-tests.md
> ```

> **Copiar este superprompt:**
> - **macOS:** `pbcopy < superprompts/desarrollo/generador-tests.md`
> - **Linux:** `xclip -selection clipboard < superprompts/desarrollo/generador-tests.md`
> - **Windows:** `clip < superprompts/desarrollo/generador-tests.md`

---

## generador-tests

### Versión Markdown (HTML)

Actúa como un <span style="color: #4CAF50;">**Ingeniero de Calidad de Software (QA Engineer)**</span> y desarrollador, experto en automatización de pruebas y metodologías como TDD y BDD.

**[CONTEXTO]**
- **Framework de Testing:** <span style="color: #FF9800;">`{{framework_testing}}`</span> (Ej: "Jest con React Testing Library", "Vitest", "Pytest", "Cypress", "Playwright").
- **Tipo de Test:** <span style="color: #FF9800;">`{{tipo_de_test}}`</span> (Ej: "Unitario", "De Integración", "End-to-End (E2E)").

**[CÓDIGO A TESTEAR]**
Pega aquí el código de la función, componente o clase para la que necesitas tests.
```<span style="color: #FF9800;">{{lenguaje}}</span>
{{pega_tu_codigo_aqui}}
```

**[REQUISITOS DE LOS TESTS]**
Describe los escenarios clave que deben ser cubiertos por los tests.
- **Caso de Éxito:** <span style="color: #FF9800;">`{{escenario_exito_1}}`</span> (Ej: "El componente debe renderizar el texto 'Hola Mundo' cuando se le pasa la prop `name='Mundo'`").
- **Caso de Éxito:** <span style="color: #FF9800;">`{{escenario_exito_2}}`</span> (Ej: "La función debe devolver la suma de dos números").
- **Caso de Borde/Error:** <span style="color: #FF9800;">`{{escenario_error_1}}`</span> (Ej: "La función debe lanzar un error si el divisor es cero").
- **Caso de Borde/Error:** <span style="color: #FF9800;">`{{escenario_error_2}}`</span> (Ej: "El componente no debe llamar a `onSubmit` si el email es inválido").
- **(Para E2E) Flujo de Usuario:** <span style="color: #FF9800;">`{{flujo_usuario}}`</span> (Ej: "El usuario va a la página de login, introduce credenciales inválidas, ve un mensaje de error, introduce credenciales válidas y es redirigido al dashboard").

**[FORMATO DE SALIDA]**
1.  **Estrategia de Test:** Un breve resumen de qué se va a testear y por qué.
2.  **Mocks y Preparación (si aplica):** Código necesario para mockear dependencias (ej: llamadas a API, librerías externas).
3.  **Código de los Tests:** El archivo de test completo (`*.test.js`, `*.spec.ts`, etc.) con todos los casos de prueba descritos, siguiendo las mejores prácticas del framework de testing. Cada test debe tener una descripción clara (`it('should do...')`).

**[RESTRICCIONES]**
- Los tests deben ser independientes entre sí.
- Apunta a una alta cobertura de código de la unidad/función proporcionada.
- <span style="color: #FF9800;">`{{cualquier_otra_restriccion}}`</span>

---

### Versión para Terminal (ANSI)

```ansi
[1;32mActúa como un Ingeniero de Calidad de Software (QA Engineer) y desarrollador, experto en automatización de pruebas.[0m

[1m[CONTEXTO][0m
- [1mFramework de Testing:[0m [1;33m`{{framework_testing}}`[0m (Ej: "Jest con React Testing Library").
- [1mTipo de Test:[0m [1;33m`{{tipo_de_test}}`[0m (Ej: "Unitario").

[1m[CÓDIGO A TESTEAR][0m
[1;33m```{{lenguaje}}
{{pega_tu_codigo_aqui}}
```[0m

[1m[REQUISITOS DE LOS TESTS][0m
Describe los escenarios a cubrir:
- [1mCaso de Éxito:[0m [1;33m`{{escenario_exito_1}}`[0m
- [1mCaso de Borde/Error:[0m [1;33m`{{escenario_error_1}}`[0m
- [1m(Para E2E) Flujo de Usuario:[0m [1;33m`{{flujo_usuario}}`[0m

[1m[FORMATO DE SALIDA][0m
1.  [1mEstrategia de Test:[0m Breve resumen.
2.  [1mMocks y Preparación:[0m Código para mockear dependencias.
3.  [1mCódigo de los Tests:[0m El archivo de test completo y bien descrito.

[1m[RESTRICCICCIONES][0m
- Los tests deben ser independientes.
- [1;33m`{{cualquier_otra_restriccion}}`[0m
```

---

## ⚡ Funciones rápidas para este proyecto

### Alias para usar este prompt
```bash
# alias sp-test="pbcopy < ~/superprompts/desarrollo/generador-tests.md && echo 'Copiado: Prompt Generador de Tests'"
# Para Linux
# alias sp-test="xclip -selection clipboard < ~/superprompts/desarrollo/generador-tests.md && echo 'Copiado: Prompt Generador de Tests'"
```

### Crear un archivo de test para un componente
```bash
function new-test() {
  if [ -z "$1" ]; then
    echo "Uso: new-test /ruta/al/componente.tsx"
    return 1
  fi

  FILE_PATH=$1
  # Extrae el nombre base y la extensión
  BASENAME=$(basename "$FILE_PATH")
  DIRNAME=$(dirname "$FILE_PATH")
  FILENAME_NO_EXT="${BASENAME%.*}"
  
  # Construye el nombre del archivo de test
  TEST_FILE_PATH="${DIRNAME}/${FILENAME_NO_EXT}.test.tsx" # o .spec.tsx, etc.

  touch "$TEST_FILE_PATH"

  echo "Archivo de test creado en: $TEST_FILE_PATH"
  echo "Ahora, usa 'sp-test' y pega el contenido de '$FILE_PATH' en la IA."
  
  # code "$TEST_FILE_PATH"
}
```
