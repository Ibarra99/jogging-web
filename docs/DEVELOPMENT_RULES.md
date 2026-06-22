# Development Rules — Jogging Web

## Objetivo

Este archivo define reglas técnicas para desarrollar la web de Jogging sin romper decisiones del proyecto.

## Stack permitido

* Astro
* TypeScript
* Tailwind CSS
* Sanity
* GitHub
* Vercel

## Estilos

Usar Tailwind CSS para:

* Layout
* Responsive
* Spacing
* Colores
* Estados hover, focus y active
* Animaciones simples

No usar:

* CSS Modules
* SCSS
* Bootstrap
* Librerías de UI no aprobadas

Se permite `src/styles/global.css` solo para:

* Importar Tailwind
* Fuentes globales
* Variables globales
* Ajustes base inevitables

## JavaScript y frameworks

Por defecto, usar componentes Astro.

No agregar React al proyecto salvo que exista una necesidad real y esté justificada.

No agregar librerías de animación como GSAP, Framer Motion o similares en esta V1.

## Home interactiva

La Home debe ser una escena full viewport basada en la ilustración final del escritorio.

Para la V1, usar el enfoque:

* Imagen base optimizada
* Hotspots accesibles encima
* Navegación por teclado
* Hover, focus y tap
* Fallback usable en mobile

No inventar funciones para objetos no confirmados.

El botón “MENÚ” debe abrir navegación.

El monitor está pendiente de definición.

El botón de sonido está pendiente de definición.

No implementar audio hasta que esté confirmado.

## Accesibilidad

Todo elemento interactivo debe ser:

* Un `<button>` si ejecuta una acción
* Un `<a>` si navega a otra sección o página

Cada hotspot debe tener:

* `aria-label`
* Estado focus visible
* Área clickeable usable
* Comportamiento compatible con teclado

No depender solo del hover.

Debe funcionar con:

* Mouse
* Teclado
* Tap en mobile

## Responsive

La web debe funcionar correctamente en:

* Desktop
* Tablet
* Mobile

La Home debe usar unidades seguras para viewport, preferentemente `svh`.

Las secciones deben poder leerse correctamente aunque la experiencia interactiva de la Home cambie en mobile.

## CMS Sanity

Sanity está previsto para administrar contenido.

No crear schemas definitivos sin validación.

Los schemas iniciales deben marcarse como propuesta técnica.

No inventar campos innecesarios.

No inventar flujos editoriales.

## Contenido

No inventar contenido final.

No inventar casos de portfolio.

No inventar textos comerciales definitivos.

Si falta contenido, marcar como:

`Pendiente de definición`

## Performance

Priorizar:

* Imágenes optimizadas
* Carga rápida
* Poco JavaScript en cliente
* Lazy loading cuando corresponda
* HTML semántico

Evitar:

* Assets pesados innecesarios
* Videos cargados automáticamente
* Librerías grandes sin justificación

## Reglas para agentes

Antes de modificar archivos, el agente debe respetar:

* `PROJECT_CONTEXT.md`
* `DEVELOPMENT_RULES.md`
* `DECISIONS.md` si existe
* `ARCHITECTURE.md` si existe

El agente no debe:

* Cambiar el stack
* Agregar dependencias sin pedirlo
* Crear rutas no solicitadas
* Inventar comportamiento
* Reestructurar todo el proyecto sin autorización
* Eliminar archivos existentes sin justificarlo

## Validaciones

Después de cambios técnicos importantes, ejecutar:

* `npm run build`

Si existe script de chequeo, también ejecutar:

* `npm run check`

Todo error debe corregirse o informarse claramente.
