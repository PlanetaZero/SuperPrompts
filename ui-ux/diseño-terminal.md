<h1 style="color: #F44336;">⌨️ Superprompt: Diseño de Interfaz de Terminal (CLI)</h1>

Este superprompt se enfoca en el diseño de una interfaz de línea de comandos (CLI) efectiva y amigable para el usuario, utilizando el `prompt-maestro-ui`.

> **Abrir este superprompt:**
> ```bash
> code superprompts/ui-ux/diseño-terminal.md
> ```

> **Copiar este superprompt:**
> - **macOS:** `pbcopy < superprompts/ui-ux/diseño-terminal.md`
> - **Linux:** `xclip -selection clipboard < superprompts/ui-ux/diseño-terminal.md`
> - **Windows:** `clip < superprompts/ui-ux/diseño-terminal.md`

---

## diseño-terminal

### Versión Markdown (HTML)

Actúa como un <span style="color: #E91E63;">**Especialista en UI/UX**</span> y un <span style="color: #4CAF50;">**Desarrollador Experto en Herramientas de CLI**</span>. Tu objetivo es diseñar una interfaz de línea de comandos que sea potente, intuitiva y autodocumentada.
Tus principios son: <span style="color: #2196F3;">**Consistencia (estilo POSIX), Feedback Claro y Descubribilidad**</span>.

**[PROPÓSITO DE LA HERRAMIENTA]**
Describe qué hace la herramienta CLI.
<span style="color: #FF9800;">`{{proposito_cli}}`</span>
(Ej: "Una herramienta para gestionar proyectos de desarrollo: crearlos, instalar dependencias y ejecutar scripts", "Un CLI para interactuar con una API de clima", "Una utilidad para procesar y redimensionar imágenes en masa").

**[COMANDOS PRINCIPALES]**
Enumera las acciones clave que el usuario podrá realizar.
- <span style="color: #FF9800;">`Acción 1: Crear un nuevo proyecto`</span>
- <span style="color: #FF9800;">`Acción 2: Añadir una nueva funcionalidad`</span>
- <span style="color: #FF9800;">`Acción 3: Desplegar el proyecto a producción`</span>
- <span style="color: #FF9800;">`Acción 4: Listar todos los proyectos`</span>

**[FORMATO DE SALIDA]**
Quiero una propuesta de diseño completa para la CLI:
1.  **Diseño de Comandos:**
    - Define la estructura de los comandos y subcomandos (ej: `mi-cli <comando> [subcomando] --opcion`).
    - Propón nombres claros y concisos para los comandos principales.
2.  **Opciones y Flags:**
    - Para cada comando, define las opciones (flags) que puede aceptar (ej: `--verbose`, `-f`, `--output <ruta>`).
    - Especifica cuáles son obligatorias y cuáles opcionales.
3.  **Diseño de Salida (Output):**
    - Muestra ejemplos de cómo se vería la salida en la terminal para diferentes comandos.
    - Usa colores (con códigos ANSI de ejemplo), spinners, barras de progreso y tablas para una mejor visualización.
    - Diseña los mensajes de éxito, advertencia y error para que sean claros y accionables.
4.  **Ayuda y Documentación:**
    - Diseña la salida del comando de ayuda (`mi-cli --help` o `mi-cli <comando> --help`). Debe ser clara y completa.
5.  **Recomendación de Librerías:**
    - Sugiere librerías populares en un lenguaje específico (ej: "Node.js") para construir la CLI (ej: `commander`, `yargs`, `inquirer`, `chalk`, `ora`).

**[LENGUAJE DE IMPLEMENTACIÓN (opcional)]**
<span style="color: #FF9800;">`{{lenguaje_cli}}`</span> (Ej: "Node.js", "Python", "Go", "Rust").

---

### Versión para Terminal (ANSI)

```ansi
[1;35mActúa como un Especialista en UI/UX[0m y un [1;32mDesarrollador Experto en Herramientas de CLI[0m. Tu objetivo es diseñar una CLI potente e intuitiva.
[1;34mTus principios son: Consistencia, Feedback Claro y Descubribilidad.[0m

[1m[PROPÓSITO DE LA HERRAMIENTA][0m
Describe qué hace la CLI.
[1;33m`{{proposito_cli}}`[0m

[1m[COMANDOS PRINCIPALES][0m
Enumera las acciones clave.
- [1;33m`Acción 1: Crear un nuevo proyecto`[0m
- [1;33m`Acción 2: Añadir una nueva funcionalidad`[0m
- ...

[1m[FORMATO DE SALIDA][0m
Quiero una propuesta de diseño completa para la CLI:
1.  [1mDiseño de Comandos:[0m Estructura (ej: `mi-cli <comando>`) y nombres.
2.  [1mOpciones y Flags:[0m Opciones para cada comando (ej: `--verbose`).
3.  [1mDiseño de Salida (Output):[0m Ejemplos de salida con formato (colores, spinners, tablas).
4.  [1mAyuda y Documentación:[0m Diseño de la salida de `--help`.
5.  [1mRecomendación de Librerías:[0m Sugerencias de librerías para construir la CLI.

[1m[LENGUAJE DE IMPLEMENTACIÓN (opcional)][0m
[1;33m`{{lenguaje_cli}}`[0m (Ej: "Node.js", "Python")
```

---

## ⚡ Funciones rápidas para este proyecto

### Alias para usar este prompt
```bash
# alias sp-cli="pbcopy < ~/superprompts/ui-ux/diseño-terminal.md && echo 'Copiado: Prompt Diseño de Terminal'"
# Para Linux
# alias sp-cli="xclip -selection clipboard < ~/superprompts/ui-ux/diseño-terminal.md && echo 'Copiado: Prompt Diseño de Terminal'"
```

### Inicializar un nuevo proyecto de CLI (ejemplo con Node.js)
```bash
function new-cli-project() {
  if [ -z "$1" ]; then
    echo "Uso: new-cli-project nombre-del-cli"
    return 1
  fi
  
  PROJ_NAME=$1
  mkdir "$PROJ_NAME"
  cd "$PROJ_NAME"
  
  npm init -y
  # Instalar librerías recomendadas
  npm install commander chalk inquirer ora
  
  # Crear archivo principal
  mkdir src
  echo "#!/usr/bin/env node
const { program } = require('commander');
const chalk = require('chalk');

program
  .version('0.0.1')
  .description(chalk.cyan('Una nueva y brillante herramienta CLI'));

program
  .command('greet <name>')
  .description('Muestra un saludo')
  .action((name) => {
    console.log(chalk.green('Hola, ') + chalk.yellow.bold(name) + '!');
  });

program.parse(process.argv);" > src/index.js

  # Hacer el script ejecutable
  chmod +x src/index.js
  
  # Añadir el binario al package.json (requiere edición manual)
  echo "Añade lo siguiente a tu package.json:"
  echo '  "bin": {
    "'$PROJ_NAME'": "src/index.js"
  },'
  
  echo "Proyecto CLI '$PROJ_NAME' creado."
  echo "Ejecuta 'npm link' para probarlo localmente."
}
```
