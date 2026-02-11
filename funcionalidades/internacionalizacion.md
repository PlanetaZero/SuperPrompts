# <span style="color:#00FF66">🌍 SUPERPROMPT: INTERNACIONALIZACIÓN (i18n)</span>

## 🧩 Descripción
Este superprompt te guía para implementar soporte multi-idioma (internacionalización o i18n) en una aplicación web, desde la estructura de archivos hasta la integración en los componentes.

---

## <span style="color:#00E5FF">🧠 Instrucciones para la IA</span>
Actúa como un **Desarrollador Frontend Senior** con experiencia en la internacionalización (i18n) y localización (l10n) de aplicaciones a gran escala.

**[TAREA]**
Proporciona una guía completa y el código necesario para añadir soporte i18n a mi proyecto.

**1. CONTEXTO DEL PROYECTO:**
- **Framework:** `{{framework}}` (Ej: "React", "Next.js", "Vue 3").
- **Idiomas Objetivo:** `{{lista_de_idiomas}}` (Ej: "Inglés (en), Español (es), Francés (fr)").
- **Idioma por Defecto:** `{{idioma_por_defecto}}` (Ej: "en").
- **Librería i18n preferida (opcional):** `{{libreria_i18n}}` (Ej: "i18next", "react-intl", "vue-i18n"). Si no se especifica, recomienda la más popular para el framework.

**[FORMATO DE SALIDA]**
Quiero una implementación completa:
1.  **Recomendación de Librería e Instalación:** Justifica la elección de la librería y proporciona el comando de instalación.
2.  **Estructura de Archivos:** Muestra la estructura de carpetas recomendada para los archivos de traducción (ej: `public/locales/en/translation.json`).
3.  **Configuración Inicial:** Proporciona el código para el archivo de configuración de i18n (ej: `i18n.js`), donde se inicializa la librería, se definen los idiomas soportados y se configura el detector de idioma (ej: del navegador, de la URL).
4.  **Archivos de Traducción (Ejemplo):** Muestra un ejemplo de un archivo `translation.json` para un par de idiomas, con algunas claves de ejemplo.
5.  **Integración en la Aplicación:** Muestra cómo envolver la aplicación principal para que el contexto de i18n esté disponible en todos los componentes.
6.  **Uso en un Componente:** Proporciona un ejemplo de un componente de React/Vue que use un hook (ej: `useTranslation`) para mostrar texto traducido.
7.  **Selector de Idioma:** Muestra el código para un componente simple que permita al usuario cambiar de idioma.

---

## <span style="color:#FFEB3B">🟦 Versión Terminal (ANSI)</span>
```bash
echo -e "
\e[32m🌍 SUPERPROMPT: INTERNACIONALIZACIÓN (i18n)\e[0m

\e[36m### INSTRUCCIONES PARA LA IA ###\e[0m
Actúa como un Desarrollador Frontend Senior experto en i18n. Guíame para añadir soporte multi-idioma a mi proyecto.

\e[33m[CONTEXTO DEL PROYECTO:]\e[0m
- Framework: \e[33m`{{framework}}`\e[0m
- Idiomas Objetivo: \e[33m`{{lista_de_idiomas}}`\e[0m
- Idioma por Defecto: \e[33m`{{idioma_por_defecto}}`\e[0m
- Librería i18n (opcional): \e[33m`{{libreria_i18n}}`\e[0m

Tu respuesta debe incluir: Recomendación de librería, Estructura de archivos, Configuración inicial, Ejemplos de archivos de traducción, Integración, Uso en un componente y un Selector de idioma.
"
```

---

## 🟣 Comandos rápidos (modo app)
**Abrir este archivo:**
```bash
code superprompts/funcionalidades/internacionalizacion.md
```

**Copiar este superprompt:**
- **macOS:** `pbcopy < superprompts/funcionalidades/internacionalizacion.md`
- **Linux:** `xclip -selection clipboard < superprompts/funcionalidades/internacionalizacion.md`

---

## 🛠️ Funciones rápidas
```bash
# Función para crear la estructura básica de carpetas de locales
function init-i18n() {
  if [ "$#" -eq 0 ]; then
    echo "Uso: init-i18n en es fr de..."
    return 1
  fi
  
  echo "Creando estructura de carpetas para i18n en ./public/locales/"
  for lang in "$@"; do
    mkdir -p "./public/locales/$lang"
    echo "{
  \"welcome_message\": \"Bienvenido a nuestra aplicación\",
  \"greeting\": \"Hola, {{name}}\" 
}" > "./public/locales/$lang/translation.json"
    echo "Creado: ./public/locales/$lang/translation.json"
  done
  echo "\nEstructura i18n creada. No olvides traducir los archivos .json."
}
```

---

## 🗂️ Notas adicionales
- La internacionalización es más que solo traducir texto. También implica adaptar formatos de fecha, números y monedas. Las librerías como `i18next` suelen manejar esto.
- Considera usar un servicio de gestión de traducciones (TMS) como Lokalise o Crowdin si el proyecto es grande.
