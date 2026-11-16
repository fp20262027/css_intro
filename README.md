# Práctica CSS Bloque 1

## Transformación visual del Campus Tecnológico Prometeo

**Modalidad:** trabajo individual  
**Archivos de partida:** `index.html`  
**Archivo que debes crear:** `css/estilos.css`

## Situación de partida

El equipo del Campus Tecnológico Prometeo ha preparado el contenido de su nueva página web. El documento HTML contiene toda la información necesaria, pero todavía no tiene una presentación visual adecuada.

Tu trabajo consiste en diseñar la página mediante una hoja de estilos externa. Debes mejorar su legibilidad, organización visual y coherencia sin utilizar todavía sistemas avanzados de maquetación.

La estructura HTML ya está preparada. Antes de modificarla, intenta resolver cada requisito utilizando los selectores CSS adecuados.


## Estructura del proyecto

Organiza los archivos de esta manera:

```text
apellido_nombre_css/
├── index.html
└── css/
    └── estilos.css
```

No cambies la ruta del archivo CSS incluida en el HTML.

## Restricciones

En esta práctica no puedes utilizar:

- Flexbox.
- CSS Grid.
- Posicionamiento mediante `position`.
- Media queries.
- Animaciones o transiciones.
- Frameworks o bibliotecas CSS.
- JavaScript.
- La declaración `!important`.
- Estilos en línea mediante el atributo `style`.

Puedes modificar el HTML únicamente cuando sea necesario para añadir una clase reutilizable o corregir un error. No debes eliminar contenido ni reconstruir la página.

## Fase 1. Preparación de la hoja de estilos

1. Crea la carpeta `css`.
2. Dentro de ella, crea el archivo `estilos.css`.
3. Comprueba que la hoja de estilos está correctamente enlazada.
4. Añade un comentario inicial que incluya tu nombre y una descripción breve del archivo.
5. Incluye al principio de la hoja:

```css
*, *::before, *::after {
  box-sizing: border-box;
}
```

6. Declara en `:root`, como mínimo, las siguientes variables:

- Color principal.
- Color secundario.
- Color del texto.
- Color de fondo general.
- Color de superficie para secciones o tarjetas.
- Espaciado habitual.
- Radio de borde.

Ejemplo de estructura, sin valores obligatorios:

```css
:root {
  --color-principal: ...;
  --color-secundario: ...;
  --color-texto: ...;
  --color-fondo: ...;
  --color-superficie: ...;
  --espacio: ...;
  --radio: ...;
}
```

Las variables deben utilizarse posteriormente en varias reglas. No basta con declararlas.

## Fase 2. Estilos generales

Aplica un estilo general a la página teniendo en cuenta estos requisitos:

1. Define en `body`:
   - Familia tipográfica.
   - Color del texto.
   - Color de fondo.
   - Tamaño de texto base.
   - Interlineado.
   - Eliminación o ajuste del margen predeterminado.

2. Crea una jerarquía visual clara para:
   - `h1`.
   - `h2`.
   - `h3`.
   - `h4`.

3. Los párrafos deben resultar cómodos de leer.
4. Los enlaces deben distinguirse del texto normal sin depender únicamente del color.
5. El contenido principal no debe ocupar todo el ancho de la ventana. Utiliza `width` o `max-width` y márgenes automáticos cuando corresponda.

## Fase 3. Cabecera y navegación

Estiliza la cabecera principal y la navegación.

La cabecera debe:

- Diferenciarse claramente del contenido.
- Utilizar el color principal o secundario.
- Tener suficiente espacio interior.
- Mostrar una jerarquía clara entre la etiqueta del curso, el título y el subtítulo.

La navegación debe:

- Mostrar los enlaces de forma clara.
- Diferenciar los estados normal, visitado, al pasar el ratón y al recibir el foco.
- Mantener siempre visible el foco de teclado.
- Utilizar el selector descendiente o el selector de hijo directo en alguna regla.

No utilices Flexbox ni Grid para colocar los enlaces.

## Fase 4. Secciones y avisos

Aplica una presentación coherente a las secciones del contenido principal.

1. Todas las secciones con clase `.seccion` deben compartir:
   - Fondo o superficie.
   - Espacio interior.
   - Separación exterior.
   - Borde o radio de borde.

2. La clase `.seccion-etiqueta` debe funcionar como una etiqueta visual secundaria.
3. El aviso `.aviso-importante` debe destacar sobre el contenido que lo rodea.
4. El aviso no puede diferenciarse exclusivamente mediante un cambio de color.
5. Utiliza al menos una propiedad heredada desde un elemento padre.

## Fase 5. Tarjetas de itinerarios

Convierte cada elemento `.curso` en una tarjeta visual.

Cada tarjeta debe utilizar:

- Fondo.
- `padding`.
- `border`.
- `margin`.
- `border-radius`.
- Una anchura o anchura máxima adecuada.

Además:

1. Diferencia la tarjeta `.destacado`.
2. Diferencia la tarjeta `.curso-recomendado`.
3. Diferencia el curso marcado como `.proximamente`.
4. El botón deshabilitado debe parecer inactivo, pero continuar siendo legible.
5. La duración y el nivel del curso deben tener una presentación secundaria.
6. Utiliza un pseudoelemento `::before` o `::after` para añadir una marca visual a la tarjeta recomendada.
7. Utiliza un selector de atributo para aplicar algún estilo según `data-nivel`.

Ejemplos de elementos que puedes seleccionar:

```css
.curso { }
.curso-recomendado { }
.curso[data-nivel="inicial"] { }
.curso-recomendado::before { }
```

## Fase 6. Competencias y noticias

Estiliza los bloques de competencias y noticias.

Debes conseguir que:

- Todas las competencias compartan una apariencia común.
- La primera competencia tenga algún detalle diferente mediante una pseudoclase estructural.
- Las noticias tengan separación y jerarquía interna.
- `.noticia-urgente` destaque sobre las demás.
- Las fechas tengan un estilo secundario.
- Los enlaces de las noticias tengan estados `:hover` y `:focus-visible`.

Utiliza, como mínimo, una de estas pseudoclases:

```css
:first-child
:last-child
:nth-child()
:not()
```

## Fase 7. Tabla de talleres

La tabla debe ser fácil de consultar.

Aplica estilos a:

- La tabla completa.
- El título `caption`.
- La cabecera `thead`.
- Las celdas `th` y `td`.
- Las filas del cuerpo.
- La fila `.sesion-destacada`.

Requisitos:

1. Utiliza `border-collapse`.
2. Añade espacio interior a las celdas.
3. Distingue visualmente la cabecera.
4. Aplica un estilo alterno a las filas pares o impares mediante `:nth-child()`.
5. Añade un estado visual a las filas cuando el puntero pasa sobre ellas.
6. La sesión destacada debe seguir siendo reconocible aunque se elimine el color de fondo.
7. Los encabezados y los datos deben conservar una alineación coherente.

## Fase 8. Recursos y enlaces

Estiliza las listas de recursos y descargas.

Debes utilizar selectores de atributo para distinguir:

- Enlaces externos.
- Enlaces de descarga.
- Enlaces de correo electrónico.
- Enlaces internos que comienzan por `#`.

Puedes utilizar selectores como:

```css
a[rel="external"] { }
a[download] { }
a[href^="mailto:"] { }
a[href^="#"] { }
```

Añade una señal visual mediante `::before` o `::after` a uno de estos tipos de enlace. La señal generada debe ser breve y no sustituir al texto del enlace.

## Fase 9. Preguntas frecuentes

Estiliza los elementos `details` y `summary`.

Requisitos:

- Cada pregunta debe distinguirse como un bloque independiente.
- `summary` debe parecer interactivo.
- Debe existir un estado visible al pasar el ratón.
- Debe existir un foco de teclado claramente visible.
- Utiliza el selector de atributo `[open]` para diferenciar una pregunta desplegada.

Ejemplo:

```css
details[open] { }
```

## Fase 10. Formulario de inscripción

El formulario debe tener una presentación clara y accesible.

Estiliza:

- `form`.
- `fieldset`.
- `legend`.
- `label`.
- `input`.
- `select`.
- `textarea`.
- Botones.
- Grupos `.campo-formulario` y `.opcion-formulario`.

Utiliza pseudoclases y selectores para mostrar distintos estados:

```css
input[required] { }
input:focus-visible { }
input:valid { }
input:invalid { }
input:checked { }
button:hover { }
button:focus-visible { }
button:disabled { }
```

Condiciones obligatorias:

1. El foco debe verse claramente en campos, botones y enlaces.
2. Los campos válidos e inválidos deben distinguirse sin depender exclusivamente del color.
3. El texto de `placeholder` debe diferenciarse del contenido introducido.
4. El botón principal y el botón secundario deben tener distinta jerarquía visual.
5. Los botones deben tener estado `:hover` y `:focus-visible`.
6. Las etiquetas deben seguir siendo visibles. No las sustituyas por el `placeholder`.

## Fase 11. Pie de página

El pie debe cerrar visualmente la página y diferenciarse del contenido principal.

Aplica estilos a:

- Fondo y texto del pie.
- Navegación secundaria.
- Enlaces del pie.
- Texto legal.

Utiliza un selector descendiente para evitar que sus enlaces tengan exactamente el mismo aspecto que los de la navegación principal.

## Fase 12. Cascada y especificidad

Añade temporalmente estas reglas al final de tu hoja:

```css
p {
  color: #444;
}

#itinerarios .curso p {
  color: #555;
}

.curso p {
  color: var(--color-texto);
}
```

Realiza las siguientes tareas:

1. Predice qué regla controla el color de los párrafos de las tarjetas.
2. Escribe la especificidad de cada selector.
3. Comprueba el resultado mediante DevTools.
4. Localiza la declaración que aparece tachada.
5. Modifica tus selectores para obtener el resultado deseado.
6. No utilices `!important`.
7. Cuando termines la comprobación, conserva únicamente las reglas necesarias.

## Fase 13. Comprobación con DevTools

Antes de entregar, utiliza las herramientas del navegador para localizar:

- La regla que establece el color final de un título.
- Una propiedad heredada desde `body`.
- El valor calculado de `font-size` en un párrafo.
- El tamaño final de una tarjeta.
- Una declaración sobrescrita por otra regla.
- El archivo y la línea de los que procede una propiedad.

Realiza al menos una modificación temporal desde DevTools y trasládala después al archivo `estilos.css`.

## Requisitos técnicos mínimos

Tu hoja debe contener, como mínimo:

- Un selector universal.
- Selectores de etiqueta.
- Cinco selectores de clase.
- Un selector de identificador.
- Tres selectores de atributo diferentes.
- Un selector descendiente.
- Un selector de hijo directo.
- Un selector de hermano.
- Una agrupación de selectores.
- Tres pseudoclases de interacción o formulario.
- Dos pseudoclases estructurales.
- Un pseudoelemento.
- Variables CSS utilizadas en varias reglas.
- Propiedades tipográficas.
- Unidades absolutas y relativas utilizadas con sentido.
- Propiedades del modelo de caja.
- Al menos una propiedad heredada intencionadamente.

## Ampliaciones opcionales

Realiza estas tareas solo si has completado todos los requisitos:

### Ampliación A. Segundo tema

Crea una segunda combinación visual modificando únicamente las variables de `:root`. No dupliques todas las reglas.

### Ampliación B. Selectores adicionales

Utiliza alguno de estos selectores:

```css
a[href$=".pdf"] { }
.curso:not(.destacado) { }
.curso:nth-of-type(2) { }
```

### Ampliación C. Documentación

Añade comentarios breves para separar las secciones principales de la hoja:

```css
/* Estilos generales */
/* Cabecera y navegación */
/* Itinerarios */
/* Tabla */
/* Formulario */
```

## Entrega

Entrega una carpeta comprimida.
```

La carpeta debe contener:

```text
apellido_nombre_css/
├── index.html
└── css/
    └── estilos.css
```

No incluyas archivos que no se utilicen.