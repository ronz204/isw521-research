# ¿Qué es y qué problema concreto resuelve?

**Definición técnica**  
Tailwind CSS es un framework de CSS basado en el paradigma *utility-first*: en lugar de proveer componentes visuales prediseñados, expone un conjunto exhaustivo de clases atómicas de bajo nivel —cada una mapea directamente a una única propiedad CSS— que se componen en el HTML para construir cualquier interfaz sin abandonar el marcado.

**El problema que resuelve**  
El flujo de trabajo CSS tradicional genera dos fricciones estructurales. Primero, la **colisión de nombres y el efecto cascada**: al crecer un proyecto, los selectores de distintos módulos se pisan entre sí, forzando el uso de convenciones como BEM o la acumulación de especificidad para evitar regresiones. Segundo, la **divergencia entre marcado y estilo**: los archivos `.css` separados del HTML crean una indirección que dificulta entender qué reglas afectan a qué elemento y hace que eliminar estilos obsoletos sea riesgoso.

**Cómo lo resuelve**  
Al colocar las clases utilitarias directamente en el elemento HTML, el estilo queda co-localizado con la estructura. No existen selectores globales que colisionen; cada clase tiene un único efecto predecible. Adicionalmente, su compilador JIT (*Just-In-Time*) analiza estáticamente el código fuente y genera **únicamente** las clases utilizadas, eliminando por completo el CSS muerto sin requerir configuración manual de purga.