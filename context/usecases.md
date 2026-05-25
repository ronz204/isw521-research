# Casos de uso

## Cuándo conviene usarlo

**Arquitectura basada en componentes**  
Ideal para frameworks modernos como Vue, React o Svelte, donde el marcado y la lógica ya están encapsulados. El acoplamiento estrecho de Tailwind a la estructura del componente potencia la modularidad.

**Proyectos con diseño altamente personalizado**  
Cuando el equipo de diseño provee un sistema visual a medida que cambia constantemente. Al no imponer opiniones estéticas, Tailwind otorga un control *pixel-perfect* absoluto.

**Sistemas de alto rendimiento**  
Aplicaciones donde los tiempos de carga son críticos y se requiere optimizar el ancho de banda, eliminando todo el CSS sin usar.

---

## Cuándo no conviene usarlo

**Desarrollo sin componentización**  
En sitios masivos construidos con HTML estático sin motores de templates, modificar el diseño requeriría editar clases en miles de elementos duplicados, violando el principio DRY.

**Equipos sin conocimiento sólido de CSS**  
Tailwind no enseña CSS, es un atajo para escribirlo. Sin comprender conceptos como Grid, Flexbox, especificidad o posicionamiento, la interfaz colapsará rápidamente bajo una pila incomprensible de clases utilitarias.