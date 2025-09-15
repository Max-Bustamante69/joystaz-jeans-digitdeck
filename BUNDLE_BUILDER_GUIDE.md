# Bundle Builder - Guía de Implementación

## Descripción General

El Bundle Builder es una sección completa de Shopify que permite a los usuarios crear bundles personalizados con descuentos progresivos y regalos gratuitos. La implementación incluye:

### Características Principales

1. **Grid Layout Responsivo**: 3/4 para productos, 1/4 para bundle steps
2. **Steps Dinámicos**: Configurables desde el theme editor con descuentos y códigos
3. **Selección de Productos**: Integración con product-card existente
4. **Bundle Management**: Añadir/remover productos del bundle
5. **Collection Tabs Carousel**: Filtrado de productos por colección con navegación horizontal
6. **Free Gift Siempre Visible**: Regalo con estados bloqueado/desbloqueado
7. **Add to Cart**: Funcionalidad completa con aplicación de descuentos

## Archivos Creados/Modificados

### 1. `sections/bundle-builder.liquid`

- Sección principal con toda la funcionalidad
- Schema completo y customizable
- JavaScript integrado para manejo del bundle
- Estilos CSS incluidos

### 2. `snippets/product-card.liquid` (Modificado)

- Agregado soporte para `bundle_mode`
- Nuevo botón "Añadir al Bundle"
- Funcionalidad para enviar productos al bundle
- Feedback visual al añadir productos

### 3. `templates/page.bundle-builder.json`

- Template configurado con 4 steps por defecto
- Configuración lista para usar
- Códigos de descuento pre-configurados

## Configuración Requerida

### 1. Colección "Bundle"

Crear una colección llamada `bundle` con los productos disponibles para bundles.

### 2. Códigos de Descuento en Shopify

Crear los siguientes códigos de descuento en el admin de Shopify:

- `BUNDLE5` - 5% de descuento
- `BUNDLE10` - 10% de descuento
- `BUNDLE15` - 15% de descuento
- `BUNDLE20` - 20% de descuento

### 3. Producto de Regalo (Opcional)

Seleccionar un producto para usar como regalo gratuito cuando se completen todos los steps.

## Funcionalidades

### Steps del Bundle

- **Configurables**: Título, porcentaje de descuento, código de descuento
- **Visuales**: Iconos de candado que se activan al añadir productos
- **Secuenciales**: Cada step toma exactamente 1 producto (1er producto = Step 1, 2do producto = Step 2, etc.)

### Gestión de Productos

- **Selección de Color/Talla**: Funciona igual que el product-card normal
- **Añadir al Bundle**: Botón azul distintivo en modo bundle
- **Visualización**: Los productos aparecen en el step correspondiente
- **Remover**: Botón X para quitar productos del bundle

### Free Gift

- **Condicional**: Solo aparece si se habilita y se completan todos los steps
- **Automático**: Se añade automáticamente al carrito
- **Visual**: Diseño dorado distintivo con animación

### Add to Cart

- **Bundle Completo**: Añade todos los productos seleccionados
- **Aplicación de Descuento**: Aplica automáticamente el código correspondiente
- **Propiedades**: Añade metadatos para identificar productos del bundle

## Personalización

### Theme Editor

- Títulos y descripciones
- Configuración de colección
- Límite de productos
- Textos del carrito
- Configuración de regalo gratuito
- Configuración de garantía

### Steps (Bloques)

- Texto del step
- Porcentaje de descuento (0-50%)
- Código de descuento de Shopify

## Integración con Carrito

### Propiedades Añadidas

```javascript
properties: {
  '_bundle_step': stepNumber,
  '_bundle_discount': discountPercentage,
  '_bundle_free_gift': 'true' // Solo para regalo
}
```

### Eventos Disparados

- `cart:updated` - Actualiza el estado del carrito
- `cart:open` - Abre el drawer del carrito

## Estilos y Animaciones

### CSS Incluido

- Gradientes de fondo
- Transiciones suaves
- Hover effects
- Animación de regalo (pulse-glow)
- Responsive design
- Efectos de activación de steps

### Responsive Design

- Mobile-first approach
- Grid adaptativo
- Botones táctiles optimizados
- Spacing responsivo

## Uso

1. **Crear página**: Crear una página con template `page.bundle-builder`
2. **Configurar colección**: Asegurar que existe la colección `bundle`
3. **Códigos de descuento**: Crear los códigos en Shopify admin
4. **Personalizar**: Usar el theme editor para ajustar textos y configuraciones
5. **Producto regalo**: Seleccionar producto de regalo si se desea

## Consideraciones Técnicas

### Dependencias

- Alpine.js (para reactividad)
- Tailwind CSS (para estilos)
- Swiper.js (para carouseles de producto)

### Compatibilidad

- Shopify 2.0 themes
- Modern browsers
- Mobile responsive
- Touch-friendly

### Performance

- Lazy loading de imágenes
- Transiciones optimizadas
- Event delegation
- Minimal DOM manipulation

## Futuras Mejoras

### Posibles Extensiones

1. **Analytics**: Tracking de conversión de bundles
2. **A/B Testing**: Diferentes configuraciones de steps
3. **Inventory Management**: Verificación de stock en tiempo real
4. **Social Proof**: Reviews y ratings de bundles
5. **Upselling**: Sugerencias de productos relacionados
6. **Wishlist Integration**: Guardar bundles para después
7. **Share Functionality**: Compartir bundles configurados

### Optimizaciones

1. **Caching**: Cache de configuración de productos
2. **Preloading**: Precargar imágenes de productos
3. **Service Worker**: Funcionalidad offline básica
4. **Progressive Enhancement**: Funcionalidad sin JavaScript

## Soporte

## Nuevas Funcionalidades Implementadas

### Collection Tabs Carousel

- **Filtrado Inteligente**: Extrae automáticamente las colecciones de los productos del bundle
- **Navegación Horizontal**: Carousel con flechas de navegación cuando hay muchas tabs
- **Responsive Design**: Se adapta al número de colecciones y tamaño de pantalla
- **Animaciones Suaves**: Transiciones al cambiar entre colecciones
- **Estado Activo**: Indica visualmente la colección seleccionada

### Free Gift Mejorado

- **Siempre Visible**: La tarjeta del regalo aparece desde el inicio
- **Estado Bloqueado**:
  - Colores grises y opacidad reducida
  - Icono de candado superpuesto
  - Texto "Completa todos los steps para desbloquearlo"
- **Estado Desbloqueado**:
  - Animación dorada pulsante
  - Checkmark verde en la imagen del producto
  - Texto "¡Desbloqueado! 🎉"
  - Se añade automáticamente al carrito

### Mejoras Técnicas

- **Performance**: Filtrado eficiente con visibilidad condicional
- **UX**: Feedback visual inmediato al cambiar filtros
- **Accessibility**: Estados claros para usuarios con discapacidades
- **Mobile First**: Optimizado para dispositivos móviles

Para soporte técnico o modificaciones, contactar al equipo de desarrollo con:

- Descripción del issue
- Pasos para reproducir
- Browser y dispositivo
- Screenshots si es necesario
