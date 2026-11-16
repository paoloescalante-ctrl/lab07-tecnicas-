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

| Aspecto | Detalle |
|---------|---------|
| Técnica agregada | Role prompting (desarrollador Java senior para un equipo de trabajo) y formato de respuesta definido. |
| Por qué | En la v1 la IA decidió sola el formato y no sabía para quién escribía. Con el rol y el formato pedido la respuesta debía ser más ordenada y predecible. |
| Qué mejoró | Respetó el formato pedido (descripción, `@param`, `@return` y ejemplo), la descripción quedó más breve y el ejemplo de uso quedó dentro del Javadoc. |
| Qué faltó | Usó `@example`, que no es una etiqueta estándar de Javadoc. Mostró el resultado como `318.60`, que Java no imprimiría así con un `double`. Agregó una nota que no pedí. No mostró su razonamiento ni se revisó a sí misma. |

## Version 3: prompt final

## Tecnicas usadas en el prompt final

## Evaluacion del resultado

## Por que elegi estas tecnicas