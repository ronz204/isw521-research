# Tailwind CSS vs. Bootstrap

| Característica | Tailwind CSS | Bootstrap |
|---|---|---|
| **Enfoque de diseño** | *Utility-First* — ladrillos básicos: `flex`, `bg-white`, `p-4` | Componentes estilizados preconstruidos: `.btn`, `.card`, `.navbar` |
| **Flexibilidad visual** | Máxima — sin opiniones estéticas; cualquier layout sin CSS custom | Rígida — requiere sobreescribir estilos por defecto con alta especificidad |
| **Tamaño del bundle** | Óptimo (~5–15 KB); el compilador JIT solo genera lo que se usa | Monolítico o modular por Sass; carga componentes completos aunque no se usen |
| **Curva de aprendizaje** | Media-alta — requiere dominio fluido del CSS moderno subyacente | Baja — basta con copiar la estructura HTML de la documentación oficial |
| **Mantenimiento a largo plazo** | Excelente — estilos encapsulados en el componente; cambios locales no rompen layouts globales | Complejo — sobreescribir estilos en hojas externas puede causar conflictos de cascada y especificidad |