<h1 style="color: #673AB7;">🏗️ Superprompt: Arquitectura General de Aplicación</h1>

Este superprompt está diseñado para solicitar una propuesta de arquitectura completa para un nuevo proyecto de software, utilizando el `prompt-maestro-arquitecto`. Es una plantilla lista para rellenar y obtener una base sólida para tu aplicación.

> **Abrir este superprompt:**
> ```bash
> code superprompts/arquitectura/arquitectura-general.md
> ```

> **Copiar este superprompt:**
> - **macOS:** `pbcopy < superprompts/arquitectura/arquitectura-general.md`
> - **Linux:** `xclip -selection clipboard < superprompts/arquitectura/arquitectura-general.md`
> - **Windows:** `clip < superprompts/arquitectura/arquitectura-general.md`

---

## arquitectura-general (Ejemplo Relleno)

### Versión Markdown (HTML)

Actúa como un <span style="color: #9C27B0;">**Arquitecto de Software Principal**</span>. Tu visión va más allá del código; defines los cimientos sobre los cuales se construirá todo el sistema.
Tus pilares son: <span style="color: #2196F3;">**Escalabilidad, Mantenibilidad, Seguridad y Coherencia**</span>.

**[PROPÓSITO DEL SISTEMA]**
<span style="color: #FF9800;">`Se requiere diseñar una plataforma de e-commerce para la venta de productos artesanales. Será una aplicación web pública con un panel de administración para los vendedores. Se espera un tráfico inicial de 5,000 usuarios/día, con picos estacionales.`</span>

**[REQUISITOS CLAVE]**
- **Funcionales:** <span style="color: #FF9800;">`Gestión de productos (CRUD), carrito de la compra, procesamiento de pagos (integración con Stripe), sistema de reviews de productos, perfiles de usuario y vendedor, dashboard de ventas para vendedores.`</span>
- **No Funcionales:** <span style="color: #FF9800;">`La web debe cargar en menos de 2 segundos. La plataforma debe ser responsive y accesible (WCAG AA). Los datos de los usuarios deben estar encriptados. El sistema debe poder escalar para soportar un 50% más de tráfico durante promociones.`</span>

**[STACK TECNOLÓGICO (opcional)]**
<span style="color: #FF9800;">`Se prefiere un stack basado en JavaScript/TypeScript. Abierto a sugerencias sobre frontend, backend y base de datos. Se valora el uso de tecnologías modernas y con buena comunidad.`</span>

**[FORMATO DE SALIDA]**
Quiero una propuesta de arquitectura detallada:
1.  **Visión General de la Arquitectura:** Un diagrama o descripción de alto nivel del patrón arquitectónico elegido (Ej: Monolito modular, Microservicios, Arquitectura Hexagonal). Justifica la elección.
2.  **Propuesta de Stack Tecnológico:** Lista de tecnologías (lenguajes, frameworks, bases de datos, etc.) con una justificación para cada una.
3.  **Estructura de Carpetas Detallada:** Un árbol de directorios completo que refleje la arquitectura propuesta.
4.  **Patrones de Diseño Clave:** Ejemplos de patrones (Ej: Inyección de Dependencias, Repository, CQRS) que deberían usarse y dónde.
5.  **Estrategia de Datos:** Cómo se almacenarán, gestionarán y accederán los datos.
6.  **Consideraciones de Seguridad y Escalabilidad:** Puntos clave a tener en cuenta durante el desarrollo.

**[RESTRICCIONES]**
<span style="color: #FF9800;">`El equipo de desarrollo es pequeño (3-4 personas), por lo que la arquitectura no debe tener una complejidad operativa excesiva.`</span>

---

### Versión para Terminal (ANSI)

```ansi
[1;35mActúa como un Arquitecto de Software Principal. Tu visión va más allá del código; defines los cimientos sobre los cuales se construirá todo el sistema.[0m
[1;34mTus pilares son: Escalabilidad, Mantenibilidad, Seguridad y Coherencia.[0m

[1m[PROPÓSITO DEL SISTEMA][0m
[1;33m`Se requiere diseñar una plataforma de e-commerce para la venta de productos artesanales. Será una aplicación web pública con un panel de administración para los vendedores. Se espera un tráfico inicial de 5,000 usuarios/día, con picos estacionales.`[0m

[1m[REQUISITOS CLAVE][0m
- [1mFuncionales:[0m [1;33m`Gestión de productos (CRUD), carrito de la compra, procesamiento de pagos (integración con Stripe), sistema de reviews de productos, perfiles de usuario y vendedor, dashboard de ventas para vendedores.`[0m
- [1mNo Funcionales:[0m [1;33m`La web debe cargar en menos de 2 segundos. La plataforma debe ser responsive y accesible (WCAG AA). Los datos de los usuarios deben estar encriptados. El sistema debe poder escalar para soportar un 50% más de tráfico durante promociones.`[0m

[1m[STACK TECNOLÓGICO (opcional)][0m
[1;33m`Se prefiere un stack basado en JavaScript/TypeScript. Abierto a sugerencias sobre frontend, backend y base de datos. Se valora el uso de tecnologías modernas y con buena comunidad.`[0m

[1m[FORMATO DE SALIDA][0m
Quiero una propuesta de arquitectura detallada:
1.  [1mVisión General de la Arquitectura:[0m Un diagrama o descripción de alto nivel del patrón arquitectónico elegido.
2.  [1mPropuesta de Stack Tecnológico:[0m Lista de tecnologías y su justificación.
3.  [1mEstructura de Carpetas Detallada:[0m Un árbol de directorios completo.
4.  [1mPatrones de Diseño Clave:[0m Ejemplos de patrones a usar.
5.  [1mEstrategia de Datos:[0m Cómo se gestionarán los datos.
6.  [1mConsideraciones de Seguridad y Escalabilidad:[0m Puntos clave.

[1m[RESTRICCIONES][0m
[1;33m`El equipo de desarrollo es pequeño (3-4 personas), por lo que la arquitectura no debe tener una complejidad operativa excesiva.`[0m
```

---

## ⚡ Funciones rápidas para este proyecto

### Alias para usar este prompt
```bash
# alias sp-arq-gen="pbcopy < ~/superprompts/arquitectura/arquitectura-general.md && echo 'Copiado: Prompt Arquitectura General'"
# Para Linux
# alias sp-arq-gen="xclip -selection clipboard < ~/superprompts/arquitectura/arquitectura-general.md && echo 'Copiado: Prompt Arquitectura General'"
```

### Guardar una nueva propuesta de arquitectura
```bash
function save-architecture() {
  if [ -z "$1" ]; then
    echo "Uso: save-architecture nombre-del-proyecto"
    return 1
  fi
  
  PROJ_NAME=$1
  DOCS_DIR="docs/architecture"
  mkdir -p "$DOCS_DIR"
  
  # Pega la respuesta de la IA en un nuevo archivo.
  # El portapapeles debería contener la propuesta generada por la IA.
  touch "${DOCS_DIR}/${PROJ_NAME}-architecture-proposal-$(date +%Y-%m-%d).md"
  
  echo "Archivo de propuesta creado en ${DOCS_DIR}/${PROJ_NAME}-architecture-proposal-$(date +%Y-%m-%d).md"
  echo "Pega el contenido de la IA en este archivo."
  
  # Para macOS, podría intentar pegar directamente:
  # pbpaste > "${DOCS_DIR}/${PROJ_NAME}-architecture-proposal-$(date +%Y-%m-%d).md"
  # Para Linux:
  # xclip -selection clipboard -o > "${DOCS_DIR}/${PROJ_NAME}-architecture-proposal-$(date +%Y-%m-%d).md"
}
```
