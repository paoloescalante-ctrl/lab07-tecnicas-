# Tarea: Mi prompt avanzado


## Tarea elegida

Documentar una funcion Java con comentarios Javadoc usando una IA. La funcion calcula el total de una compra: aplica un descuento y luego suma el 18 % de IGV.

```java
public static double calcularTotal(double precio, int cantidad, double descuento) {
    double conDescuento = precio * (1 - descuento);
    double conIgv = conDescuento * 1.18;
    return conIgv * cantidad;
}
```

## Version 1: prompt basico

```text
Documenta esta funcion:
public static double calcularTotal(double precio, int cantidad, double descuento) {
    double conDescuento = precio * (1 - descuento);
    double conIgv = conDescuento * 1.18;
    return conIgv * cantidad;
}
```
| Aspecto | Detalle |
|---------|---------|
| Técnica agregada | Ninguna, es un prompt básico. |
| Por qué | Es el punto de partida para comparar las siguientes versiones. |
| Qué mejoró / qué respondió la IA | Documentó bien la función con Javadoc, `@param`, `@return` y un ejemplo de uso. |
| Qué faltó | No definí el formato, así que la IA agregó cosas por su cuenta (ejemplo y nota). El resultado que mostró (318.60) no es lo que Java imprimiría con un `double` (318.6). No explicó su razonamiento, no se revisó a sí misma y no indicó para quién escribía la documentación. |

## Version 2

```text
Actua como desarrollador Java senior que documenta codigo para un equipo de trabajo.
Documenta esta funcion con comentarios Javadoc. Formato: descripcion de una linea, @param por cada parametro, @return y un ejemplo de uso.
Responde en espanol.
public static double calcularTotal(double precio, int cantidad, double descuento) {
    double conDescuento = precio * (1 - descuento);
    double conIgv = conDescuento * 1.18;
    return conIgv * cantidad;
}
```
## Version 3: prompt final

```text
<rol>Actua como desarrollador Java senior que documenta codigo para un equipo de trabajo.</rol>
<contexto>La funcion calcula el total de una compra en una tienda peruana: aplica un descuento y luego suma el 18 % de IGV sobre el precio con descuento.</contexto>
<ejemplo>
Funcion: public static int sumar(int a, int b) { return a + b; }
/**
 * Suma dos numeros enteros.
 *
 * @param a primer numero
 * @param b segundo numero
 * @return la suma de a y b
 *
 * <pre>
 * int r = sumar(2, 3); // r vale 5
 * </pre>
 */
</ejemplo>
<tarea>Piensa paso a paso que hace cada linea de la funcion y calcula a mano el resultado del ejemplo de uso con precio 120, cantidad 3 y descuento 0.25. Luego escribe el Javadoc. Antes de responder, revisa tu documentacion: usa solo etiquetas estandar de Javadoc y verifica que el resultado del ejemplo sea correcto.
public static double calcularTotal(double precio, int cantidad, double descuento) {
    double conDescuento = precio * (1 - descuento);
    double conIgv = conDescuento * 1.18;
    return conIgv * cantidad;
}</tarea>
<formato>1) Razonamiento en pasos numerados. 2) Bloque Javadoc con descripcion de una linea, @param por cada parametro, @return y ejemplo de uso dentro de <pre>. 3) Una linea final que diga que corregiste en la revision. No agregues notas extra. Responde en espanol.</formato>
```

| Parte del prompt | Técnica |
|------------------|---------|
| `<rol>` | Role prompting |
| `<contexto>`, `<tarea>`, `<formato>` | Prompt estructurado |
| `<ejemplo>` | Few-shot |
| "Piensa paso a paso... calcula a mano" | Chain of thought |
| "Antes de responder, revisa tu documentación" | Autocrítica |

## Evaluacion del resultado

| Criterio | Cumple (Sí / No) |
|----------|------------------|
| ¿Muestra el razonamiento en pasos numerados? | Sí |
| ¿Tiene `@param` para los 3 parámetros y `@return`? | Sí |
| ¿El resultado del ejemplo es correcto (318,60)? | Sí |
| ¿Usa solo etiquetas estándar de Javadoc? | Sí |
| ¿Respeta el formato pedido y no agrega notas extra? | Sí |
| ¿Menciona casos límite (descuento mayor a 1, cantidad negativa)? | No |

## Por que elegi estas tecnicas

Elegí role prompting porque la documentación debía estar escrita para un equipo de trabajo, y un rol concreto me ayuda a fijar el tono y el nivel técnico. Usé few-shot porque un ejemplo de Javadoc le muestra a la IA el formato exacto que quiero, sin depender de que lo adivine. Usé chain of thought porque la función tiene un orden importante (primero el descuento y luego el IGV), y al pedir los cálculos a mano pude comprobar cada paso yo mismo. Agregué autocrítica porque en la versión 2 la IA cometió errores que no detectó sola, como usar una etiqueta no estándar y mostrar un resultado que Java no imprimiría. Usé el prompt estructurado para que el rol, el contexto, el ejemplo y el formato no se mezclaran. No usé descomposición porque la tarea es una sola función pequeña y no necesitaba dividirse en varios pedidos.