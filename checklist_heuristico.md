# Checklist Heurístico - Rappi iOS (Auditoría Nielsen)

| ID       | Heurística violada                              | Pantalla / contexto                          | Descripción del problema                                                                 | Evidencia                        | Severidad |
|----------|-------------------------------------------------|----------------------------------------------|------------------------------------------------------------------------------------------|----------------------------------|-----------|
| H1-A     | H8 - Estética y diseño minimalista             | Home principal (pantalla de inicio)          | Sobrecarga visual extrema con múltiples banners animados, promociones flash, cupones y categorías superpuestos al mismo tiempo. Genera alta carga cognitiva, distracción y dificultad para encontrar restaurantes rápidamente, causando abandono inmediato en primer contacto. | evidencia_02_home_sobrecarga.png | 4         |
| H2-A     | H8 - Estética y diseño minimalista             | Home - Sección de banners y promociones      | Animaciones constantes y elementos superpuestos (promos + sugerencias) ralentizan percepción de velocidad y confunden al usuario en móvil pequeño, violando minimalismo. | evidencia_03_banners_animados.png | 4         |
| H3-A     | H7 - Flexibilidad y eficiencia de uso          | Home - Búsqueda y categorías                 | No hay búsqueda sticky o atajo destacado para "repedir último pedido", obligando scroll excesivo en home sobrecargado, reduciendo eficiencia para usuarios frecuentes. | evidencia_05_busqueda_scroll.png | 2         |
| H4-B     | H4 - Consistencia y estándares                 | Menú restaurante - Botón "Agregar al carrito" | Botón "Agregar" tiene estilo diferente (tamaño/color) al botón "Hacer pedido" en checkout, violando consistencia en iOS y confudiendo flujo de compra. | evidencia_08_agregar_button.png | 4         |
| H5-B     | H5 - Prevención de errores                     | Menú restaurante - Selección de productos    | Permite agregar productos sin indicar stock real o advertencia clara; error aparece tarde (en carrito o checkout), llevando a frustración y posible abandono. | evidencia_09_stock_no_visible.png | 3         |
| H6-B     | H6 - Reconocimiento antes que recuerdo         | Carrito - Lista de productos                 | Miniaturas y precios claros ayudan, pero nombres de productos truncados en vista compacta obligan recordar detalles, afectando reconocimiento rápido. | evidencia_11_carrito_truncado.png | 1         |
| H7-C     | H1 - Visibilidad del estado del sistema        | Checkout - Proceso de pago                   | Spinner indefinido sin texto explicativo, tiempo estimado ni pasos (ej. "Confirmando restaurante"), dejando al usuario sin saber qué pasa y generando ansiedad. | evidencia_12_spinner_pago.png | 3         |
| H8-C     | H3 - Control y libertad del usuario            | Post-confirmación pedido                     | No hay botón directo para cancelar pedido confirmado (solo chat soporte enterrado), quitando libertad al usuario para corregir errores sin proceso largo. | evidencia_15_cancelar_dificil.png | 3         |
| H9-C     | H9 - Ayudar a reconocer, diagnosticar y recuperarse de errores | Checkout - Error en pago                     | Mensaje genérico "Algo salió mal" sin explicación ni acciones (ej. "Reintentar" o "Cambiar tarjeta"), impidiendo recuperación rápida y frustrando al usuario. | evidencia_17_error_generico.png | 3         |
| H10-C    | H10 - Ayuda y documentación                    | Checkout - Durante o después de error        | Centro de ayuda difícil de encontrar (enterrado en menú lateral), no accesible directamente desde error o checkout, dejando al usuario sin soporte inmediato. | evidencia_19_ayuda_enterrada.png | 2         |
| H11-C    | H1 - Visibilidad del estado del sistema        | Checkout - Confirmación de dirección         | No muestra feedback claro si dirección es inválida o fuera de zona, permitiendo avanzar y fallar tarde, sin visibilidad de estado real del sistema. | evidencia_20_direccion_no_feedback.png | 3         |
| H12-B    | H4 - Consistencia y estándares                 | Carrito - Botones de edición/eliminar        | Iconos y botones de edición (editar cantidad/eliminar) inconsistentes en tamaño y estilo con el resto de la app, violando estándares y confudiendo acciones. | evidencia_21_carrito_inconsistente.png | 3         |

**Resumen:**
- Total hallazgos: 12
- Heurísticas cubiertas: H1, H3, H4, H5, H6, H7, H8, H9, H10 (más de 5 requeridas)
- Distribución: Flujo A (3), Flujo B (4), Flujo C (5)
- Severidad promedio: ~2.9 (moderado-grave)
- Prioridades altas: H8 (sobrecarga) y H4 (inconsistencia)


