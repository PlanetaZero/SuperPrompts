<h1 style="color: #673AB7;">🧩 Superprompt: Patrones de Código</h1>

Este superprompt se utiliza para solicitar la implementación de un patrón de diseño de software específico (o una comparación entre varios) dentro de un contexto de proyecto dado.

> **Abrir este superprompt:**
> ```bash
> code superprompts/arquitectura/patrones-codigo.md
> ```

> **Copiar este superprompt:**
> - **macOS:** `pbcopy < superprompts/arquitectura/patrones-codigo.md`
> - **Linux:** `xclip -selection clipboard < superprompts/arquitectura/patrones-codigo.md`
> - **Windows:** `clip < superprompts/arquitectura/patrones-codigo.md`

---

## patrones-codigo

### Versión Markdown (HTML)

Actúa como un <span style="color: #4CAF50;">**Desarrollador de Software Experto**</span> y un <span style="color: #9C27B0;">**Arquitecto de Software**</span>, con un profundo conocimiento de los patrones de diseño (GoF, GRASP, etc.) y patrones arquitectónicos.

**[CONTEXTO DEL PROBLEMA]**
Describe el problema que intentas resolver o la funcionalidad que quieres implementar.
<span style="color: #FF9800;">`{{contexto_del_problema}}`</span>
(Ej: "Necesito gestionar el estado global de mi aplicación React de forma centralizada", "Quiero desacoplar mi lógica de negocio del acceso a la base de datos", "Tengo un objeto complejo que requiere muchos pasos de configuración para su creación").

**[PATRÓN DE DISEÑO]**
Especifica el patrón o los patrones sobre los que quieres aprender o que quieres implementar.
<span style="color: #FF9800;">`{{patron_de_diseno}}`</span>
(Ej: "Patrón Singleton", "Patrón Repository", "Comparativa entre Factory Method y Abstract Factory", "Patrón Builder", "Patrón Observer").

**[LENGUAJE Y FRAMEWORK]**
Indica el entorno tecnológico donde se aplicará el patrón.
<span style="color: #FF9800;">`{{lenguaje_y_framework}}`</span>
(Ej: "TypeScript con React", "Python con Django", "Java con Spring Boot", "C# con .NET").

**[FORMATO DE SALIDA]**
Quiero una explicación y una implementación claras:
1.  **Explicación del Patrón:**
    - **Nombre:** Nombre del patrón.
    - **Propósito:** ¿Qué problema resuelve? (en 1-2 frases).
    - **Cuándo Usarlo:** Escenarios típicos donde este patrón es útil.
    - **Ventajas y Desventajas:** Pros y contras de su implementación.
2.  **Implementación de Ejemplo:**
    - Un ejemplo de código claro y conciso que implemente el patrón en el lenguaje/framework especificado, resolviendo el problema del contexto.
    - El código debe estar bien comentado para explicar las partes clave del patrón (el "Director", el "Builder", el "Product", etc.).
3.  **Ubicación en el Proyecto:** Una recomendación sobre en qué parte de una estructura de proyecto estándar debería vivir este código (ej: `src/common/patterns`, `src/infrastructure/repositories`).
4.  **(Si se pide comparativa) Tabla Comparativa:** Una tabla que resuma las diferencias, casos de uso, y complejidad de los patrones comparados.

---

### Versión para Terminal (ANSI)

```ansi
[1;32mActúa como un Desarrollador de Software Experto[0m y un [1;35mArquitecto de Software[0m, con un profundo conocimiento de los patrones de diseño y arquitectónicos.

[1m[CONTEXTO DEL PROBLEMA][0m
Describe el problema que intentas resolver.
[1;33m`{{contexto_del_problema}}`[0m
(Ej: "Necesito gestionar el estado global de mi aplicación React...")

[1m[PATRÓN DE DISEÑO][0m
Especifica el patrón o patrones a implementar o comparar.
[1;33m`{{patron_de_diseno}}`[0m
(Ej: "Patrón Repository", "Comparativa entre Factory Method y Abstract Factory")

[1m[LENGUAJE Y FRAMEWORK][0m
Indica el entorno tecnológico.
[1;33m`{{lenguaje_y_framework}}`[0m
(Ej: "TypeScript con React")

[1m[FORMATO DE SALIDA][0m
Quiero una explicación y una implementación claras:
1.  [1mExplicación del Patrón:[0m
    - [1mNombre:[0m Nombre del patrón.
    - [1mPropósito:[0m ¿Qué problema resuelve?
    - [1mCuándo Usarlo:[0m Escenarios típicos.
    - [1mVentajas y Desventajas:[0m Pros y contras.
2.  [1mImplementación de Ejemplo:[0m
    - Ejemplo de código claro y comentado en el lenguaje/framework especificado.
3.  [1mUbicación en el Proyecto:[0m Dónde debería vivir este código.
4.  [1m(Si se pide comparativa) Tabla Comparativa:[0m Resumen de diferencias.
```

---

## ⚡ Funciones rápidas para este proyecto

### Alias para usar este prompt
```bash
# alias sp-pattern="pbcopy < ~/superprompts/arquitectura/patrones-codigo.md && echo 'Copiado: Prompt Patrones de Código'"
# Para Linux
# alias sp-pattern="xclip -selection clipboard < ~/superprompts/arquitectura/patrones-codigo.md && echo 'Copiado: Prompt Patrones de Código'"
```

### Crear un nuevo archivo de patrón
```bash
function create-pattern-file() {
  if [ -z "$1" ] || [ -z "$2" ]; then
    echo "Uso: create-pattern-file NombrePatron [extension]"
    echo "Ejemplo: create-pattern-file Repository ts"
    return 1
  fi
  
  PATTERN_NAME=$1
  EXTENSION=${2:-"js"}
  DIR_PATH="src/patterns"
  mkdir -p "$DIR_PATH"
  
  FILE_PATH="${DIR_PATH}/${PATTERN_NAME}.${EXTENSION}"
  touch "$FILE_PATH"

  echo "Archivo para el patrón $PATTERN_NAME creado en $FILE_PATH"
  echo "Pega el código de la IA en este archivo."
  
  # Opcional: abrir el archivo con tu editor
  # code "$FILE_PATH"
}
```
