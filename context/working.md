# ¿Cómo funciona internamente?

## Arquitectura general

Tailwind no es una hoja de estilos estática que se entrega al navegador. Es un **compilador de CSS** que analiza el código fuente del proyecto y genera únicamente las reglas necesarias. Su pipeline se compone de tres etapas: escaneo, generación y optimización.

---

## Flujo de datos

**1. Escaneo del código fuente**  
El compilador recorre todos los archivos configurados (`.html`, `.vue`, `.jsx`, `.ts`, etc.) buscando cadenas de texto que coincidan con el patrón de una clase utilitaria de Tailwind. Este análisis es puramente léxico —no ejecuta el código ni construye un AST— lo que lo hace extremadamente rápido. Cada clase detectada se agrega a un conjunto de reglas a generar.

**2. Resolución de utilidades**  
Cada clase detectada se mapea contra el catálogo interno de utilidades. Por ejemplo, `p-4` resuelve a `padding: 1rem` usando la escala de espaciado del tema; `text-blue-500` resuelve al valor hexadecimal definido en la paleta de colores. Las variantes como `hover:`, `md:` o `dark:` envuelven la regla base en el selector o media query correspondiente.

**3. Generación y entrega del CSS**  
Con el conjunto de reglas resuelto, el compilador emite un único archivo CSS plano y optimizado. En desarrollo este proceso corre en modo *watch*, regenerando el CSS en milisegundos ante cada cambio. En producción se ejecuta una única vez durante el build.

---

## Mecanismo principal: el compilador JIT

Hasta la versión 2, Tailwind generaba todas las combinaciones posibles de clases en desarrollo (archivos de varios MB) y luego aplicaba PurgeCSS para eliminar las no usadas en producción. Esto creaba una discrepancia entre entornos.

A partir de la **v3** el motor *Just-In-Time* unificó ambos entornos: el CSS se genera bajo demanda a medida que se detectan clases, tanto en desarrollo como en producción. El resultado es un bundle idéntico en ambos entornos, con tamaños típicos de **5–15 KB**.

---

## Motor en v4: Oxide (Rust)

La versión **v4** reemplazó la cadena PostCSS + Node.js por **Oxide**, un compilador escrito en Rust que integra internamente un motor equivalente a *Lightning CSS*. Esto eliminó la dependencia de `postcss.config.js` y redujo los tiempos de compilación en proyectos grandes hasta en un orden de magnitud.

Además, v4 adoptó un enfoque **CSS-First**: la configuración del tema (colores, tipografía, espaciado) se declara directamente en el archivo CSS mediante variables nativas de CSS (`@theme`), en lugar de un archivo `tailwind.config.js` en JavaScript.

```css
/* Ejemplo de configuración CSS-First en v4 */
@import "tailwindcss";

@theme {
  --color-brand: #6d28d9;
  --font-sans: "Inter", sans-serif;
}
```

**Resultado:** las variables del tema quedan expuestas como *custom properties* de CSS (`var(--color-brand)`), reutilizables en cualquier parte del proyecto sin depender del compilador de Tailwind.