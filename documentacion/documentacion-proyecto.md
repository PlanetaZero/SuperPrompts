<h1 style="color: #FF5722;">📄 Superprompt: Documentación de Proyecto (README)</h1>

Este prompt genera un archivo `README.md` completo y profesional para un proyecto de software, basándose en la información del proyecto y su estructura de archivos.

> **Abrir este superprompt:**
> ```bash
> code superprompts/documentacion/documentacion-proyecto.md
> ```

> **Copiar este superprompt:**
> - **macOS:** `pbcopy < superprompts/documentacion/documentacion-proyecto.md`
> - **Linux:** `xclip -selection clipboard < superprompts/documentacion/documentacion-proyecto.md`
> - **Windows:** `clip < superprompts/documentacion/documentacion-proyecto.md`

---

## documentacion-proyecto

### Versión Markdown (HTML)

Actúa como un <span style="color: #4CAF50;">**Technical Writer**</span> y <span style="color: #4CAF50;">**Developer Advocate**</span>. Tu objetivo es crear un `README.md` claro, conciso y útil que facilite a cualquier persona (desarrolladores, usuarios, contribuidores) entender y usar este proyecto.

**[INFORMACIÓN DEL PROYECTO]**
- **Nombre del Proyecto:** <span style="color: #FF9800;">`{{nombre_del_proyecto}}`</span>
- **Descripción Corta:** <span style="color: #FF9800;">`{{descripcion_corta}}`</span> (Una frase que resuma qué hace el proyecto).
- **Stack Tecnológico:** <span style="color: #FF9800;">`{{stack_tecnologico}}`</span> (Ej: "React, Node.js, Express, PostgreSQL").
- **URL del Repositorio (opcional):** <span style="color: #FF9800;">`{{url_repo}}`</span>
- **URL de la Demo (opcional):** <span style="color: #FF9800;">`{{url_demo}}`</span>

**[ESTRUCTURA DE ARCHIVOS]**
Pega aquí la salida del comando `ls -R` o `tree` para darme contexto de la organización del proyecto.
```
{{estructura_de_archivos}}
```

**[COMANDOS CLAVE]**
Indica los comandos principales del proyecto.
- **Instalación:** `npm install`
- **Ejecutar en Desarrollo:** `npm run dev`
- **Ejecutar Tests:** `npm test`
- **Build para Producción:** `npm run build`

**[FORMATO DE SALIDA]**
Quiero un archivo `README.md` completo y bien estructurado, que incluya (si la información está disponible) las siguientes secciones:
1.  **Título y Badges:** Nombre del proyecto y badges de estado (ej: build, coverage, license). Puedes usar placeholders para los badges como `![Build Status](...)`.
2.  **Descripción:** Una descripción más detallada del proyecto. ¿Qué problema resuelve? ¿Cuáles son sus características principales?
3.  **Tabla de Contenidos.**
4.  **Características Principales (Features):** Una lista de lo que el proyecto puede hacer.
5.  **Stack Tecnológico:** Iconos o lista de las tecnologías usadas.
6.  **Requisitos Previos:** Software necesario para correr el proyecto (ej: Node.js v18+).
7.  **Instalación y Puesta en Marcha:** Guía paso a paso para instalar y ejecutar el proyecto localmente.
8.  **Uso:** Cómo usar la aplicación o librería. Ejemplos de código si aplica.
9.  **Scripts Disponibles:** Explicación de los scripts del `package.json` (o similar).
10. **Estructura del Proyecto:** Explicación de la organización de las carpetas más importantes.
11. **Cómo Contribuir:** Guía para futuros contribuidores (ej: "Forkea el repo, crea una rama, haz tus cambios y abre una Pull Request").
12. **Licencia:** Mención de la licencia del proyecto (ej: "Distribuido bajo la licencia MIT.").

---

### Versión para Terminal (ANSI)

```ansi
[1;32mActúa como un Technical Writer y Developer Advocate. Tu objetivo es crear un README.md claro, conciso y útil.[0m

[1m[INFORMACIÓN DEL PROYECTO][0m
- [1mNombre del Proyecto:[0m [1;33m`{{nombre_del_proyecto}}`[0m
- [1mDescripción Corta:[0m [1;33m`{{descripcion_corta}}`[0m
- [1mStack Tecnológico:[0m [1;33m`{{stack_tecnologico}}`[0m

[1m[ESTRUCTURA DE ARCHIVOS][0m
Pega aquí la salida de `ls -R` o `tree`.
[1;33m```
{{estructura_de_archivos}}
```[0m

[1m[COMANDOS CLAVE][0m
- [1mInstalación:[0m `npm install`
- [1mEjecutar en Desarrollo:[0m `npm run dev`
- ...

[1m[FORMATO DE SALIDA][0m
Quiero un `README.md` completo con estas secciones:
1.  [1mTítulo y Badges[0m
2.  [1mDescripción[0m
3.  [1mTabla de Contenidos[0m
4.  [1mCaracterísticas Principales[0m
5.  [1mStack Tecnológico[0m
6.  [1mRequisitos Previos[0m
7.  [1mInstalación y Puesta en Marcha[0m
8.  [1mUso[0m
9.  [1mScripts Disponibles[0m
10. [1mEstructura del Proyecto[0m
11. [1mCómo Contribuir[0m
12. [1mLicencia[0m
```

---

## ⚡ Funciones rápidas para este proyecto

### Alias para usar este prompt
```bash
# alias sp-readme="pbcopy < ~/superprompts/documentacion/documentacion-proyecto.md && echo 'Copiado: Prompt README'"
# Para Linux
# alias sp-readme="xclip -selection clipboard < ~/superprompts/documentacion/documentacion-proyecto.md && echo 'Copiado: Prompt README'"
```

### Generar README para el proyecto actual
Esta función recopila la información del proyecto actual y la formatea en el portapapeles junto con el prompt.

```bash
function generate-readme-for-this-project() {
    # Extraer nombre del proyecto del package.json (si existe)
    PROJ_NAME=$(jq -r .name package.json 2>/dev/null || basename "$PWD")
    PROJ_DESC=$(jq -r .description package.json 2>/dev/null || echo "Una breve descripción del proyecto.")
    
    # Comandos (puedes personalizarlos)
    INSTALL_CMD=$(jq -r '.scripts.install // "npm install"' package.json 2>/dev/null || echo "npm install")
    DEV_CMD=$(jq -r '.scripts.dev // "npm run dev"' package.json 2>/dev/null || echo "npm run dev")
    TEST_CMD=$(jq -r '.scripts.test // "npm test"' package.json 2>/dev/null || echo "npm test")

    # Estructura de archivos
    FILE_TREE=$(ls -R | head -n 50) # Limita la salida para no exceder el contexto

    # Prepara el contenido para el portapapeles
    CONTENT_TO_COPY=$(cat ~/superprompts/documentacion/documentacion-proyecto.md | \
        sed "s/{{nombre_del_proyecto}}/$PROJ_NAME/" | \
        sed "s/{{descripcion_corta}}/$PROJ_DESC/" | \
        sed "s/{{stack_tecnologico}}/Autodetectar según el contenido/" | \
        sed "/{{estructura_de_archivos}}/c\\$FILE_TREE" | \
        sed "s/npm install/$INSTALL_CMD/" | \
        sed "s/npm run dev/$DEV_CMD/" | \
        sed "s/npm test/$TEST_CMD/"
    )
    
    echo "$CONTENT_TO_COPY" | pbcopy # Para macOS
    # echo "$CONTENT_TO_COPY" | xclip -selection clipboard # Para Linux
    
    echo "Prompt para generar README del proyecto '$PROJ_NAME' copiado al portapapeles."
}
```
