# Bitacora de tecnicas avanzadas 
 
Laboratorio 07: Tecnicas Avanzadas de Prompting. 
Herramienta de IA usada: (escribe aqui cual usaste) 
 
## Ejercicio 2: Zero-shot, one-shot y few-shot 
 
| Tipo | Aciertos (de 5) | Formato de la respuesta | Todas con el mismo formato (Si/No) | 
|------|-----------------|-------------------------|-----------------------------------| 
| Zero-shot |NO| DESIGUAL| NO| 
| One-shot | SI|ESTRUCTURADO | SI| 
| Few-shot | SI| ESTRUCTURADO | SI| 


## Ejercicio 3: Chain of Thought 
 | Pedido |Respuesta de la IA | Muestra los pasos (Sí/No) | Correcta (Sí/No) |
|--------|--------------------|---------------------------|------------------|
| Directo | Solo mostro el numero | No muestras como llego a ese proceso | Si |
| Paso a paso | Demuestra todo el proceso | Si | Si |

 
## Ejercicio 4: Role prompting 

| Version | Vocabulario (sencillo/tecnico) | Usa ejemplos o codigo | A quien le sirve mas | 
|---------|-------------------------------|-----------------------|---------------------| 
| A. Sin rol | Es muy sencillo y poco tecnico| Si usa ejemplos, pero elegi el codigo que ella quiere| Creo que solo para aquellas que tengan una idea vaga| 
| B. Rol docente |Usa mas tecnicismo y especificaciones | Usa no solo ejemplos sino que imagenes| A un estudiante que recien empieza | 
| C. Rol senior | Vuelve a la sencilles, pero es mas puntual| Usa ejemplos e incluso deja modificar un codigo de ejemplo| A un estudiante regular | 

 
## Ejercicio 5: Descomposicion 


Voy a crear un sistema de inventario para una tienda pequena en Java. Lista los 5 requisitos principales del sistema. 
Con esos requisitos, disena las clases necesarias. Para cada clase indica sus atributos con su tipo de dato. 
Escribe el codigo Java de la clase Producto con sus atributos, un constructor y los metodos get y set. 
Revisa el codigo de la clase Producto y propone 3 mejoras concretas. D
 
## Ejercicio 6: Prompt estructurado y autocritica 
Dame casos de prueba para un login. 

<rol>Actua como analista de pruebas de software.</rol> 
<contexto>Login web con correo y contrasena. La cuenta se bloquea despues de 3 intentos fallidos.</contexto> 
<tarea>Piensa paso a paso que puede fallar y escribe 6 casos de prueba.</tarea> 
<formato>Tabla con las columnas: ID, escenario, datos de entrada, resultado esperado.</formato> 

Revisa tu tabla: faltan casos limite como campos vacios, correo sin @ o contrasena con espacios? Agrega los que falten e indica cuales agregaste. 

| Qué revisar | Cumple (Sí / No) |
|-------------|------------------|
| ¿Tiene las 4 columnas pedidas? | Si |
| ¿Incluye el bloqueo después de 3 intentos? | Si CP-04 |
| ¿Incluye casos con campos vacíos? | si CP-07,Cp08-CP09 |
| ¿Indica qué casos agregó en la autocrítica? | SI CP-07 a CP-11 |
| ¿Hay algún caso repetido o que no tenga sentido? | NO |