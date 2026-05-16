# Design System - Intranet Universidad Norbert Wiener

## 1. Tipografía
- **Títulos y Encabezados**: `Lato`, sans-serif (Weights: 400, 700, 900)
- **Cuerpo de texto e inputs**: `Roboto`, sans-serif (Weights: 400, 500, 700)

## 2. Paleta de Colores

### Colores Principales
- **Primary Teal (Principal)**: `#0F848F`
- **Primary Hover**: `#0b6770` o `#09A5B1`
- **Black (Secundario/Botones)**: `#222222`
- **Background Body**: `#F4F6F8` (Fondo general de la intranet)
- **Background Content**: `#FFFFFF` (Fondo de tarjetas y contenedores)

### Textos
- **Text Dark (Títulos principales)**: `#222222` o `#000000`
- **Text Gray (Descripciones y etiquetas)**: `#5B6E80` o `#404040`
- **Text Light (Placeholder/Inactivo)**: `#9AA6B2`

### Bordes y Divisores
- **Border Default**: `#C6CFD7`
- **Border Light**: `#E6F3F4`

### Estados y Semántica
- **Success / Asistencias**:
  - Texto/Icono: `#278B52` o `#33B56B`
  - Fondo claro: `#E7F8EF` o `#E6F3F4` (Para bloques de asistencias)
- **Warning / Inasistencias**:
  - Texto/Icono: `#F59E0B` o `#FBBF24`
  - Fondo claro: `#FFF3E0`
- **Danger / Error**:
  - Texto/Icono: `#D32F2F` o `#E22731`
  - Fondo claro: `#FFEBEE`

## 3. Tags de Modalidad
Se usan para identificar la modalidad de un curso, con un border-radius tipo pill (`16px` o `64px`):
- **Presencial**: Fondo `#0F848F`, Texto `#FFFFFF`
- **Virtual En vivo**: Fondo `#0EA5E9`, Texto `#FFFFFF`
- **Virtual 24/7**: Fondo `#F97316`, Texto `#FFFFFF`

## 4. Botones
- **Radius general**: `6px`
- **Padding general**: `12px 24px`
- `.btn-primary`: Fondo `#0F848F`, Texto `#FFFFFF`
- `.btn-black`: Fondo `#222222`, Texto `#FFFFFF`
- `.btn-outline`: Borde `#C6CFD7`, Fondo transparente, Texto `#5B6E80`
- `.btn-outline-green`: Borde `#C6CFD7`, Fondo `#FFFFFF`, Texto `#278B52` (Verde). En hover el fondo pasa a `#E7F8EF` y el borde a `#278B52`.

## 5. Espaciado y Estructura
- **Contenedor Principal (`.main-content`, `.main-container`)**: `max-width: 1082px` (o similar según vista), margin auto.
- **Tarjetas (`.card`)**: 
  - `background-color: #FFFFFF;`
  - `border: 1px solid #C6CFD7;`
  - `border-radius: 8px` (o `16px` para contenedores más grandes)
  - `padding: 24px` o `32px`
- **Sombras**: Las interacciones (hover) suelen tener un `box-shadow: 0 4px 12px rgba(0,0,0,0.05);` y un leve `transform: translateY(-2px);`.

## 6. Pestañas de Navegación (Tabs)
- Contenedor `.tabs-container` con lista `ul.tabs` y elementos `li.tab`.
- **Estado inactivo**: Fondo gris claro (`#F4F6F8`), texto gris (`#5B6E80`).
- **Estado activo (`.active`)**: Fondo blanco, texto color primario (`#0F848F`), con un borde inferior destacado de `3px solid #0F848F`.
- **Interacción**: Alternancia de contenedores mediante atributos `data-target` e inyección de clases por JavaScript.

## 7. Tablas Estructuradas (Basadas en CSS Grid y Flexbox)
- En lugar de usar `<table>` tradicional, se emplean contenedores (`.custom-table`) y CSS Grid (`display: grid`) para un control preciso de la distribución horizontal.
- **Cabeceras (`.table-header-row`)**: Fondo gris claro (`#F4F6F8`), con `border-radius: 8px`, uso de `font-size: 13px` y `font-weight: 700`.
- **Filas (`.tr`)**: Separadas visualmente por `border-bottom: 1px solid #E6F3F4` con alineación vertical centrada.
- **Configuraciones Grid**: Se definen utilidades específicas por vista (ej. `.grid-cols-auditoria`, `.grid-cols-auditoria-notas`) para establecer el `grid-template-columns` exacto que cada tabla requiere en Desktop.
- **Vista Mobile (`.mobile-card`)**: Por debajo de `768px`, las filas horizontales se transforman en una lista de tarjetas verticales. Cada campo se descompone en un `.mc-row` (con un `.mc-label` a la izquierda y un `.mc-value` a la derecha) separados por un borde sutil, facilitando la lectura sin hacer scroll horizontal.

## 8. Estados Específicos de Pago
Aplicados a celdas clave (como `.vence`):
- **Pendiente (`.estado-pendiente`)**: Fondo `#FFF3F0`, Borde `#FFD0C1`.
- **Pagado (`.estado-pagado`)**: Fondo `#E6F6ED`, Borde `#C4EBD4`.

## 9. Resumen Flotante (Floating Summary Bar)
- **Uso**: Barra anclada a la parte inferior de la pantalla (`position: fixed; bottom: 0;`), útil para mostrar acciones globales y acumuladores (como totales a pagar).
- **Estilos**: Fondo blanco, sombra superior invertida (`box-shadow: 0px -4px 8px 0px rgba(0, 0, 0, 0.12);`).
- **Animación**: Oculta por defecto con `transform: translateY(100%);` y aparece deslizando hacia arriba al agregar la clase `.visible` (`transform: translateY(0);`).
- **Consideración Mobile**: Al aparecer la barra, el contenedor principal (`.table-container` o `.main-container`) debe compensar con un `padding-bottom` generoso (ej. `12rem`) para permitir que el scroll revele por completo el último registro de la vista sin quedar tapado.

## 10. Cabeceras de Página (`.page-header-flex`)
- **Estructura**: `display: flex` separando el contexto (izquierda) de las acciones (derecha).
- **Contexto**: Un ícono SVG (`40x40px`) junto al bloque de textos (`h1` de 24px y `p` descriptivo de 16px).
- **Acciones**: Botones de utilidades o estado en la parte derecha (ej. Botón Imprimir, Botón Descargar), usando layout secundario o outline. Borde inferior demarcado por un divisor `.header-divider`.

## 11. Selectores Personalizados y Animaciones
- **Estructura HTML**: Uso de bloques `.custom-select-wrapper` conteniendo un `.custom-select-trigger` (área clickeable) y `.custom-select-options` (lista desplegable con `.d-none` por defecto).
- **Animación (Ícono Rotatorio)**: La flecha del selector (`svg`) posee un `transition: transform 0.3s ease;`. Al agregarse la clase `.open` al wrapper principal, el ícono rota 180° hacia arriba (`transform: rotate(180deg);`).
- **Lógica Global JS**: Un solo módulo central controla el comportamiento de apertura y cierre de todos los selectores. Al abrir uno, se cierran automáticamente todos los demás; también se cierran al hacer clic fuera del componente o seleccionar una opción.
