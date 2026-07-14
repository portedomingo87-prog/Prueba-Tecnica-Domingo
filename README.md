# Prueba Técnica — Landing Page (HTML + CSS)

## Contexto

Este es un sitio de una sola página (landing personal de un desarrollador
ficticio) construido solo con **HTML y CSS**, sin JavaScript. Visualmente
se ve "aceptable" a primera vista, pero tiene **varios problemas reales**
a nivel de semántica, accesibilidad y layout, típicos de código que
alguien entregó rápido y nunca revisó a fondo.

Tu trabajo **no es reescribir el sitio desde cero**. Es ponerte en los
zapatos de alguien que se une a un equipo y hereda este código: tienes que
**inspeccionarlo, encontrar qué está mal y corregirlo**, manteniendo la
estructura y el diseño general.

## Cómo revisar el proyecto

Simplemente abre `index.html` en el navegador (no necesita servidor ni
instalar nada). Recomendado: usa las DevTools del navegador (inspector de
elementos, panel de Accessibility, y prueba también en modo responsive /
móvil).

## Reglas del juego

- No tienes que cambiar el contenido, los textos ni el diseño general
  (colores, tipografía, "vibe" del sitio). El objetivo es que **funcione y
  sea accesible correctamente**, no que se vea distinto.
- Está permitido reordenar CSS, cambiar selectores, cambiar etiquetas HTML
  por otras más apropiadas, agregar atributos, etc.
- Varios de estos problemas **no son errores que rompan la página** — la
  página "carga bien" en apariencia. Son cosas que un desarrollador
  cuidadoso detecta al revisar el código o al probar con teclado / mobile
  / accesibilidad.
- Prueba en una ventana angosta (mobile) y con el teclado (Tab) además de
  con el mouse.

## Tareas a resolver

### 1. Estructura semántica del documento
El sitio entero está armado a punta de `<div>` (navbar, hero, secciones,
footer...). Revisa qué etiquetas semánticas de HTML5 existen para cada una
de estas partes (encabezado, navegación, contenido principal, secciones,
pie de página) y reemplaza los `<div>` genéricos donde corresponda.

### 2. Jerarquía de encabezados
Revisa todos los `<h1>`, `<h2>`, `<h3>`, `<h4>` del documento. Hay más de
un problema aquí: hay más de un `<h1>` en la página, y en al menos un
lugar se salta un nivel de jerarquía (por ejemplo, pasar de `<h1>`
directo a `<h4>`). Corrígelo para que la jerarquía tenga sentido de arriba
a abajo.

### 3. Metadatos básicos que faltan en el `<head>`
Hay al menos dos etiquetas/atributos estándar que debería tener cualquier
página HTML moderna y que aquí no están. Uno tiene que ver con el idioma
del documento, y el otro con cómo se comporta la página en dispositivos
móviles. Encuéntralos y agrégalos.

### 4. La imagen de perfil
La imagen del avatar tiene dos problemas distintos: uno de accesibilidad
(algo que un lector de pantalla necesitaría y no tiene) y uno de
responsividad (pruébalo en una ventana angosta y verás que la imagen se
desborda de su contenedor en vez de achicarse).

### 5. Los enlaces del menú de navegación
Haz clic en cada uno de los 4 enlaces del menú superior. Uno de ellos no
te lleva a la sección correspondiente. Encuentra por qué y corrígelo.

### 6. El menú también tapa el contenido
Independientemente del bug anterior: cuando navegas a cualquier sección
usando el menú (por ejemplo "Servicios" o "Contacto"), fíjate bien en qué
parte queda el título de la sección apenas llegas. El menú superior es
fijo (`position: fixed`) y no todas las secciones tienen en cuenta ese
espacio.

### 7. El formulario de contacto
Prueba clickear cada `<label>` del formulario ("Nombre", "Correo",
"Mensaje"). Al clickear un label, el campo correspondiente debería
recibir el foco automáticamente — es una funcionalidad nativa del HTML
cuando el label y el input están correctamente asociados. Revisa cada
campo: no todos están mal, pero más de uno sí.

### 8. El botón "Enviar mensaje"
Prueba navegar el formulario completo usando solo el teclado (Tab, y
luego Enter o Espacio para "enviar"). El botón de enviar no se comporta
como un botón real. Revisa qué etiqueta se está usando y corrígelo por la
apropiada.

### 9. Las tarjetas de "Servicios"
Achica la ventana del navegador hasta un ancho de celular. Las tres
tarjetas de servicios no se adaptan: en vez de acomodarse en columna o
ajustar su tamaño, se desbordan del contenedor. Corrige el CSS para que
las tarjetas se comporten bien en pantallas angostas.

### 10. El botón del formulario se ve "apagado"
El botón "Enviar mensaje" debería verse con el mismo color de acento
(azul) que el resto del sitio, pero se ve gris. Hay una regla de CSS en
algún lugar del archivo que está sobrescribiendo el estilo correcto —
probablemente algo que alguien dejó de una prueba y olvidó borrar.
Encuéntrala y decide la forma correcta de resolver el conflicto (esto
también aplica a por qué esa regla está "ganando" sobre la otra: vale la
pena entender el problema, no solo borrar la línea).

### 11. Contraste del texto en el footer
El texto de copyright en el pie de página es casi ilegible. Ajusta el
color para que cumpla con un contraste razonable contra el fondo (no hace
falta que midas el ratio exacto de WCAG, pero debe leerse claramente).

## Qué vamos a evaluar

- Que entiendas **por qué** pasa cada problema, no solo que lo "tapes"
  visualmente (por ejemplo, la tarea 10 se puede "resolver" agregando otro
  `!important`, pero esa no es la solución correcta).
- Uso apropiado de etiquetas semánticas y jerarquía de encabezados.
- Accesibilidad básica: labels asociados, alt en imágenes, elementos
  interactivos usando las etiquetas correctas.
- CSS limpio: evitar especificidad innecesaria (IDs para estilos,
  `!important` como parche), y layout responsivo real con Flexbox/Grid.

## Flujo de trabajo esperado (Git / GitHub)

No te entregamos un repositorio ya creado — queremos ver también cómo
organizas tu propio historial de cambios. Sigue estos pasos:

1. Crea un repositorio nuevo en tu cuenta de GitHub (puede ser privado),
   por ejemplo `prueba-tecnica-html-css`.
2. Dentro de esta carpeta del proyecto, inicializa git y haz tu primer
   commit con el código **tal como lo recibiste**, antes de tocar nada:
   ```bash
   git init
   git add .
   git commit -m "chore: código base de la prueba técnica"
   git branch -M main
   git remote add origin <URL_DE_TU_REPO>
   git push -u origin main
   ```
3. A partir de ahí, resuelve **una tarea a la vez** y haz un commit por
   cada una, con un mensaje claro que diga qué corregiste. Por ejemplo:
   ```bash
   git add .
   git commit -m "fix: asociar correctamente los labels del formulario con sus inputs"
   git push
   ```
   Puedes usar el número de tarea en el mensaje si quieres, por ejemplo
   `fix(tarea-9): hacer responsivas las tarjetas de servicios`.
4. No es obligatorio, pero se valora positivamente si usas mensajes de
   commit descriptivos (formato tipo *Conventional Commits*: `fix:`,
   `refactor:`, `chore:`, etc.) en vez de mensajes genéricos como
   "cambios" o "arreglos".
5. Al terminar, comparte el link del repositorio (o agrégame como
   colaborador si lo dejaste privado).

Con esto podemos ver no solo el resultado final, sino tu proceso: en qué
orden resolviste las cosas y cómo documentaste cada cambio.

¡Éxitos!