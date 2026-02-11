<h1 style="color: #FF5722;">📝 Superprompt: Crear Memoria Técnica</h1>

Este superprompt está diseñado para generar una "memoria técnica" o un documento de diseño técnico (TDD - Technical Design Document) para una nueva funcionalidad, un proyecto o un cambio arquitectónico significativo.

> **Abrir este superprompt:**
> ```bash
> code superprompts/documentacion/crear-memoria.md
> ```

> **Copiar este superprompt:**
> - **macOS:** `pbcopy < superprompts/documentacion/crear-memoria.md`
> - **Linux:** `xclip -selection clipboard < superprompts/documentacion/crear-memoria.md`
> - **Windows:** `clip < superprompts/documentacion/crear-memoria.md`

---

## crear-memoria

### Versión Markdown (HTML)

Actúa como un <span style="color: #9C27B0;">**Arquitecto de Software**</span> y un <span style="color: #4CAF50;">**Líder Técnico**</span>. Tu tarea es tomar un conjunto de requisitos y convertirlos en un documento técnico detallado que el equipo de desarrollo pueda seguir.

**[TÍTULO DEL DOCUMENTO]**
<span style="color: #FF9800;">`{{titulo_funcionalidad_o_proyecto}}`</span>
(Ej: "Memoria Técnica: Implementación de Autenticación Multifactor (MFA)", "Documento de Diseño: Nuevo Servicio de Notificaciones Push").

**[CONTEXTO Y PROBLEMA A RESOLVER]**
Describe el "porqué" de este documento. ¿Qué problema se está solucionando? ¿Cuál es el objetivo de negocio?
<span style="color: #FF9800;">`{{contexto_y_problema}}`</span>
(Ej: "Actualmente, la seguridad de las cuentas de usuario es baja. Necesitamos añadir una capa extra de seguridad para proteger los datos del usuario y cumplir con nuevos estándares de la industria.").

**[REQUISITOS]**
Enumera los requisitos funcionales y no funcionales que debe cumplir la solución.
- **Funcionales:** <span style="color: #FF9800;">`{{requisitos_funcionales}}`</span> (Ej: "El usuario debe poder registrar un autenticador (Google Auth, etc.). Al hacer login, se le pedirá un código de 6 dígitos.").
- **No Funcionales:** <span style="color: #FF9800;">`{{requisitos_no_funcionales}}`</span> (Ej: "La validación del código debe tardar menos de 200ms. El sistema debe ser resistente a ataques de fuerza bruta.").

**[SOLUCIÓN PROPUESTA]**
Si tienes una idea de la solución técnica, descríbela a alto nivel. Si no, pide que se proponga una.
<span style="color: #FF9800;">`{{solucion_propuesta_general}}`</span>
(Ej: "Se creará un nuevo microservicio para gestionar el ciclo de vida de MFA. Se integrará con la API de login existente. Se usará la librería 'speakeasy' para la generación de códigos TOTP.").

**[FORMATO DE SALIDA]**
Quiero un documento técnico completo en formato Markdown, con las siguientes secciones:
1.  **Resumen Ejecutivo:** Una breve descripción para stakeholders no técnicos.
2.  **Glosario:** Definición de términos clave.
3.  **Objetivos y Alcance:** Qué se va a hacer y qué no se va a hacer.
4.  **Arquitectura de la Solución:** Diagrama (en ASCII/Mermaid) y descripción de los componentes, sus interacciones y el flujo de datos.
5.  **Diseño Detallado:**
    - **Cambios en la API:** Endpoints nuevos o modificados (con su request/response).
    - **Cambios en la Base de Datos:** Nuevas tablas o modificaciones al esquema (en formato SQL DDL).
    - **Componentes de Frontend:** Descripción de los nuevos componentes de UI necesarios.
6.  **Estrategia de Pruebas:** Cómo se probará la funcionalidad (unitarias, integración, E2E).
7.  **Plan de Despliegue y Rollback:** Pasos para lanzar la funcionalidad a producción y cómo revertirla si algo sale mal.
8.  **Riesgos y Mitigaciones:** Posibles problemas y cómo planeamos abordarlos.

---

### Versión para Terminal (ANSI)

```ansi
[1;35mActúa como un Arquitecto de Software[0m y un [1;32mLíder Técnico[0m. Tu tarea es crear un documento técnico detallado.

[1m[TÍTULO DEL DOCUMENTO][0m
[1;33m`{{titulo_funcionalidad_o_proyecto}}`[0m

[1m[CONTEXTO Y PROBLEMA A RESOLVER][0m
Describe el "porqué".
[1;33m`{{contexto_y_problema}}`[0m

[1m[REQUISITOS][0m
- [1mFuncionales:[0m [1;33m`{{requisitos_funcionales}}`[0m
- [1mNo Funcionales:[0m [1;33m`{{requisitos_no_funcionales}}`[0m

[1m[SOLUCIÓN PROPUESTA][0m
Describe la idea de la solución a alto nivel.
[1;33m`{{solucion_propuesta_general}}`[0m

[1m[FORMATO DE SALIDA][0m
Quiero un documento técnico completo en Markdown con estas secciones:
1.  [1mResumen Ejecutivo[0m
2.  [1mGlosario[0m
3.  [1mObjetivos y Alcance[0m
4.  [1mArquitectura de la Solución[0m (con diagrama)
5.  [1mDiseño Detallado[0m (API, DB, Frontend)
6.  [1mEstrategia de Pruebas[0m
7.  [1mPlan de Despliegue y Rollback[0m
8.  [1mRiesgos y Mitigaciones[0m
```

---

## ⚡ Funciones rápidas para este proyecto

### Alias para usar este prompt
```bash
# alias sp-tdd="pbcopy < ~/superprompts/documentacion/crear-memoria.md && echo 'Copiado: Prompt Crear Memoria Técnica'"
# Para Linux
# alias sp-tdd="xclip -selection clipboard < ~/superprompts/documentacion/crear-memoria.md && echo 'Copiado: Prompt Crear Memoria Técnica'"
```

### Crear un nuevo archivo de memoria técnica
```bash
function new-tdd() {
  if [ -z "$1" ]; then
    echo "Uso: new-tdd 'nombre-de-la-feature'"
    return 1
  fi
  
  # Convierte el nombre a un formato de archivo amigable (kebab-case)
  FILENAME=$(echo "$1" | iconv -t ascii//TRANSLIT | sed -r s/[~\^]+//g | sed -r s/[^a-zA-Z0-9]+/-/g | sed -r s/^-+\|-+$//g | tr A-Z a-z)
  
  DOCS_DIR="docs/tdd"
  mkdir -p "$DOCS_DIR"
  
  FILE_PATH="${DOCS_DIR}/${FILENAME}.md"
  touch "$FILE_PATH"

  echo "Archivo de memoria técnica creado en: $FILE_PATH"
  # code "$FILE_PATH"
}
```
