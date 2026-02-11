<h1 style="color: #2196F3;">✨ Superprompt: Mejorar Código</h1>

Este es un prompt genérico para mejorar un fragmento de código sin un objetivo de refactorización tan específico como el anterior. Es útil para una revisión general y aplicación de buenas prácticas.

> **Abrir este superprompt:**
> ```bash
> code superprompts/desarrollo/mejora-codigo.md
> ```

> **Copiar este superprompt:**
> - **macOS:** `pbcopy < superprompts/desarrollo/mejora-codigo.md`
> - **Linux:** `xclip -selection clipboard < superprompts/desarrollo/mejora-codigo.md`
> - **Windows:** `clip < superprompts/desarrollo/mejora-codigo.md`

---

## mejora-codigo (Ejemplo Relleno)

### Versión Markdown (HTML)

Actúa como un <span style="color: #00BCD4;">**Analizador Estático de Código y Experto en Refactorización**</span>. Tu tarea es recibir un bloque de código y devolver una versión mejorada, junto con una explicación clara de los cambios realizados.
Tus directivas son: <span style="color: #2196F3;">**Legibilidad, Simplicidad, Eficiencia y Mantenibilidad**</span> (principios SOLID, DRY, KISS).

**[CÓDIGO FUENTE]**
```python
# Este código calcula el precio final de un producto
def calculate_price(item_price, is_member, has_coupon, coupon_value, stock):
    if stock > 0:
        final_price = item_price
        if is_member == True:
            # 10% de descuento para miembros
            final_price = final_price * 0.9
        
        if has_coupon == True:
            # Descuento del cupón
            if final_price > coupon_value:
                final_price = final_price - coupon_value
            else:
                final_price = 0
        
        if final_price < 0:
            final_price = 0
            
        return final_price
    else:
        return "Item out of stock"
```

**[CONTEXTO (opcional)]**
<span style="color: #FF9800;">`Esta es una función de un sistema de e-commerce escrita en Python. Se usa para determinar el precio final en la página del carrito.`</span>

**[FORMATO DE SALIDA]**
Quiero la respuesta en un formato de "code review":
1.  **Análisis General:** Una evaluación de alto nivel de la calidad del código original (complejidad, legibilidad, posibles problemas como "números mágicos").
2.  **Puntos de Mejora:** Una lista detallada de los cambios que propones, explicando el "porqué" de cada uno (Ej: "He reemplazado `is_member == True` por `is_member` para mayor simplicidad", "He usado `max(0, ...)` para evitar precios negativos").
3.  **Código Refactorizado:** La versión final y mejorada del código.
4.  **Sugerencias Adicionales:** Ideas para futuras mejoras (ej: "Considera usar un objeto `DiscountStrategy` para gestionar los descuentos de forma más escalable").

**[RESTRICCIONES]**
<span style="color: #FF9800;">`Mantener la misma firma de función. El lenguaje es Python.`</span>

---

### Versión para Terminal (ANSI)

```ansi
[1;36mActúa como un Analizador Estático de Código y Experto en Refactorización.[0m
[1;34mTus directivas son: Legibilidad, Simplicidad, Eficiencia y Mantenibilidad.[0m

[1m[CÓDIGO FUENTE][0m
[1;33m```python
# Este código calcula el precio final de un producto
def calculate_price(item_price, is_member, has_coupon, coupon_value, stock):
    if stock > 0:
        final_price = item_price
        if is_member == True:
            final_price = final_price * 0.9
        
        if has_coupon == True:
            final_price = final_price - coupon_value
        
        if final_price < 0:
            final_price = 0
            
        return final_price
    else:
        return "Item out of stock"
```[0m

[1m[CONTEXTO (opcional)][0m
[1;33m`Función de un sistema de e-commerce en Python.`[0m

[1m[FORMATO DE SALIDA][0m
Quiero la respuesta en formato "code review":
1.  [1mAnálisis General.[0m
2.  [1mPuntos de Mejora[0m (explicando el porqué).
3.  [1mCódigo Refactorizado.[0m
4.  [1mSugerencias Adicionales.[0m

[1m[RESTRICCIONES][0m
[1;33m`Mantener la misma firma de función. El lenguaje es Python.`[0m
```

---

## ⚡ Funciones rápidas para este proyecto

### Alias para usar este prompt
```bash
# alias sp-improve="pbcopy < ~/superprompts/desarrollo/mejora-codigo.md && echo 'Copiado: Prompt Mejorar Código'"
# Para Linux
# alias sp-improve="xclip -selection clipboard < ~/superprompts/desarrollo/mejora-codigo.md && echo 'Copiado: Prompt Mejorar Código'"
```

### Analizar y mejorar un archivo
Similar a la función de refactorización, prepara el prompt y el código para la IA.

```bash
function improve-file() {
  if [ -z "$1" ]; then
    echo "Uso: improve-file /ruta/al/archivo.py"
    return 1
  fi

  FILE_PATH=$1
  
  COPY_CMD=""
  if command -v pbcopy &> /dev/null; then COPY_CMD="pbcopy";
  elif command -v xclip &> /dev/null; then COPY_CMD="xclip -selection clipboard";
  else echo "Comando de copia no encontrado." && return 1; fi

  (cat ~/superprompts/desarrollo/mejora-codigo.md; echo ""; echo "---"; echo "[CÓDIGO FUENTE]"; cat "$FILE_PATH") | $COPY_CMD
  
  echo "Prompt de mejora y contenido de '$FILE_PATH' copiados al portapapeles."
}
```
