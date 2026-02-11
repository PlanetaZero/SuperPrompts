<h1 style="color: #4DD0E1;">🤖 Superprompt: Clasificación con IA</h1>

Este superprompt está diseñado para implementar una funcionalidad que utiliza un modelo de lenguaje (LLM) para clasificar texto, como analizar el sentimiento de un comentario o categorizar un ticket de soporte.

> **Abrir este superprompt:**
> ```bash
> code superprompts/funcionalidades/ia-clasificacion.md
> ```

> **Copiar este superprompt:**
> - **macOS:** `pbcopy < superprompts/funcionalidades/ia-clasificacion.md`
> - **Linux:** `xclip -selection clipboard < superprompts/funcionalidades/ia-clasificacion.md`
> - **Windows:** `clip < superprompts/funcionalidades/ia-clasificacion.md`

---

## ia-clasificacion

### Versión Markdown (HTML)

Actúa como un <span style="color: #4CAF50;">**Ingeniero de Machine Learning (ML Engineer)**</span> y desarrollador de software, especializado en la integración de modelos de lenguaje (LLMs) en aplicaciones.

**[CONTEXTO]**
- **Tarea de Clasificación:** ¿Qué necesitas clasificar?
  <span style="color: #FF9800;">`{{tarea_de_clasificacion}}`</span> (Ej: "Analizar el sentimiento de los comentarios de los usuarios", "Categorizar tickets de soporte técnico", "Determinar el idioma de un texto").
- **Categorías de Salida:** ¿Cuáles son las posibles etiquetas o categorías que el modelo debe asignar?
  <span style="color: #FF9800;">`{{categorias_de_salida}}`</span> (Ej: `["Positivo", "Negativo", "Neutro"]`, `["Bug", "Pregunta", "Sugerencia"]`, `["español", "inglés", "francés"]`).
- **Entorno de Implementación:** ¿Dónde se ejecutará esta lógica?
  <span style="color: #FF9800;">`{{entorno}}`</span> (Ej: "En un backend de Node.js, como una función que se puede llamar vía API").
- **Modelo de IA Preferido:** <span style="color: #FF9800;">`{{modelo_ia}}`</span> (Ej: "API de OpenAI (gpt-3.5-turbo)", "API de Gemini", "un modelo open-source como `distilbert-base-uncased-finetuned-sst-2-english` de Hugging Face").

**[FORMATO DE SALIDA]**
Quiero el código y la estructura para implementar esta funcionalidad.
1.  **Diseño del Prompt para el LLM (si aplica):**
    - Si se usa una API como OpenAI/Gemini, diseña el "system prompt" y el "user prompt" óptimos para la tarea de clasificación, utilizando técnicas como el "few-shot learning" si es necesario. El prompt debe instruir al modelo para que devuelva la respuesta en un formato JSON estricto.
2.  **Recomendación de Librerías:**
    - Sugiere las librerías necesarias para interactuar con el modelo de IA. (Ej: `openai` para Node.js, `transformers.js` para modelos de Hugging Face en el cliente/servidor).
3.  **Código de la Función de Clasificación:**
    - Proporciona una función asíncrona (ej: `classifyText(text: string): Promise<Category>`) que tome un texto de entrada, llame al modelo de IA y devuelva la categoría predicha.
    - La función debe incluir manejo de errores, reintentos (si es una llamada de red) y validación de la respuesta del modelo.
4.  **Ejemplo de Integración:**
    - Muestra cómo se podría exponer esta función a través de un endpoint de API en un servidor Express.
    - `POST /api/classify` con body `{ "text": "Este es un comentario." }` que devuelve `{ "category": "Neutro" }`.

---

### Versión para Terminal (ANSI)

```ansi
[1;32mActúa como un Ingeniero de Machine Learning (ML Engineer) y desarrollador, especializado en la integración de LLMs.[0m

[1m[CONTEXTO][0m
- [1mTarea de Clasificación:[0m [1;33m`{{tarea_de_clasificacion}}`[0m (Ej: "Analizar el sentimiento de comentarios").
- [1mCategorías de Salida:[0m [1;33m`{{categorias_de_salida}}`[0m (Ej: `["Positivo", "Negativo", "Neutro"]`).
- [1mEntorno:[0m [1;33m`{{entorno}}`[0m (Ej: "Backend de Node.js").
- [1mModelo de IA:[0m [1;33m`{{modelo_ia}}`[0m (Ej: "API de OpenAI").

[1m[FORMATO DE SALIDA][0m
1.  [1mDiseño del Prompt para el LLM:[0m El prompt de sistema y usuario para obtener una respuesta JSON.
2.  [1mRecomendación de Librerías:[0m (Ej: `openai` para Node.js).
3.  [1mCódigo de la Función de Clasificación:[0m Una función `classifyText(text)` que llame al modelo y maneje errores.
4.  [1mEjemplo de Integración:[0m Cómo exponer la función a través de un endpoint de API en Express.
```

---

## ⚡ Funciones rápidas para este proyecto

### Alias para usar este prompt
```bash
# alias sp-classify="pbcopy < ~/superprompts/funcionalidades/ia-clasificacion.md && echo 'Copiado: Prompt Clasificación con IA'"
# Para Linux
# alias sp-classify="xclip -selection clipboard < ~/superprompts/funcionalidades/ia-clasificacion.md && echo 'Copiado: Prompt Clasificación con IA'"
```

### Instalar la librería de OpenAI para Node.js
```bash
function install-openai-node() {
    if [ -f "package.json" ]; then
        npm install openai
        echo "Librería 'openai' de Node.js instalada."
        echo "Recuerda configurar tu API key en las variables de entorno (OPENAI_API_KEY)."
    else
        echo "No se encontró package.json."
    fi
}
```
