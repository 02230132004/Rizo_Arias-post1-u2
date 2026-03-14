# Reporte de Auditoría Heurística de Usabilidad – Rappi iOS

**Estudiante:** Miguel Angel Rizo Arias  
**Asignatura:** Aplicaciones Móviles – Ingeniería de Sistemas  
**Universidad de Santander (UDES) – 2026**  
**Dispositivo:** iPhone 13 Pro (iOS 19 o superior)  
**Aplicación auditada:** Rappi – Deliveries in Minutes  
**Versión aproximada:** Última disponible en App Store (marzo 2026, ~10.x)  
**Fecha de auditoría:** Marzo 2026  

**Flujos auditados (seleccionados por criticidad):**
1. **Flujo A:** Home / onboarding inicial y búsqueda de restaurante o producto  
2. **Flujo B:** Selección de productos y agregado al carrito  
3. **Flujo C:** Checkout, confirmación de pedido y proceso de pago  

**Justificación breve de los flujos:**
Estos flujos representan el viaje completo del usuario en una app de delivery: descubrimiento → construcción del pedido → pago. Problemas en ellos generan abandono alto de carrito (>60-70% en e-commerce/delivery), baja retención y pérdida de ingresos, especialmente en un mercado competitivo como Colombia donde la velocidad y claridad son clave para la conversión.

**Metodología:**
- Recorrido de cada flujo dos veces: una como usuario normal (experiencia natural) y otra inspeccionando activamente contra las 10 heurísticas de Nielsen (1994).  
- Identificados 12 hallazgos distribuidos en los 3 flujos, cubriendo 9 heurísticas diferentes.  
- Escala de severidad: 0 (no problema) – 4 (catastrófico).  
- Evidencias: capturas de pantalla en carpeta /evidencias/.

**Resumen de hallazgos:**
- Total violaciones documentadas: 12  
- Severidad promedio: 2.9 (moderado-grave)  
- Heurísticas más afectadas: H8 (minimalismo), H4 (consistencia), H1 (visibilidad estado), H9 (recuperación errores)  
- Distribución: Flujo A (3), Flujo B (4), Flujo C (5)

## Hallazgos Detallados (principales por severidad alta)

### Severidad 4 (Catastrófico – debe arreglarse inmediatamente)
1. **ID: H1-A**  
   **Heurística:** H8 - Estética y diseño minimalista  
   **Pantalla:** Home principal (inicio de la app)  
   **Descripción:** Sobrecarga visual extrema con banners animados múltiples, promociones flash, cupones y categorías superpuestos. Genera alta carga cognitiva y distracción, haciendo difícil al usuario encontrar restaurantes o productos rápidamente. En iPhone (pantalla más pequeña que tablets), esto causa abandono inmediato en el primer contacto.  
   **Evidencia:** evidencia_02_home_sobrecarga.png  
   **Impacto:** Principal causa de churn en nuevos usuarios.

2. **ID: H2-A**  
   **Heurística:** H8 - Estética y diseño minimalista  
   **Pantalla:** Home - Sección de banners y promociones  
   **Descripción:** Animaciones constantes y elementos superpuestos ralentizan la percepción de velocidad y confunden al usuario, violando el principio de minimalismo.  
   **Evidencia:** evidencia_03_banners_animados.png  
   **Impacto:** Reduce percepción de calidad y confianza.

3. **ID: H4-B**  
   **Heurística:** H4 - Consistencia y estándares  
   **Pantalla:** Menú restaurante vs Checkout  
   **Descripción:** Botones primarios de acción ("Agregar al carrito" y "Hacer pedido") con estilos, tamaños y colores inconsistentes. Viola estándares de Apple Human Interface Guidelines y confunde al usuario en el flujo de compra.  
   **Evidencia:** evidencia_08_agregar_vs_confirmar.png  
   **Impacto:** Aumenta errores cognitivos y abandono de carrito.

### Severidad 3 (Grave – afecta significativamente la tarea)
4. **ID: H7-C**  
   **Heurística:** H1 - Visibilidad del estado del sistema  
   **Pantalla:** Checkout – Proceso de pago  
   **Descripción:** Spinner indefinido sin texto explicativo, tiempo estimado ni pasos visibles. El usuario no sabe qué está pasando, generando ansiedad y posible cancelación prematura.  
   **Evidencia:** evidencia_12_spinner_pago.png  
   **Impacto:** Frustración en momento crítico de transacción.

5. **ID: H8-C**  
   **Heurística:** H3 - Control y libertad del usuario  
   **Pantalla:** Post-confirmación de pedido  
   **Descripción:** No hay botón directo para cancelar pedido confirmado (solo opción enterrada en chat soporte). Quita libertad al usuario para corregir errores sin proceso largo.  
   **Evidencia:** evidencia_15_cancelar_dificil.png  
   **Impacto:** Mala experiencia post-compra.

6. **ID: H9-C**  
   **Heurística:** H9 - Ayudar a reconocer, diagnosticar y recuperarse de errores  
   **Pantalla:** Checkout – Error en pago  
   **Descripción:** Mensajes genéricos ("Algo salió mal") sin explicación ni acciones claras. Impide recuperación rápida y deja al usuario perdido.  
   **Evidencia:** evidencia_17_error_generico.png  
   **Impacto:** Pérdida de confianza y abandono de compra.

7. **ID: H5-B**  
   **Heurística:** H5 - Prevención de errores  
   **Pantalla:** Menú restaurante – Selección productos  
   **Descripción:** Permite agregar productos sin advertencia de stock real; error aparece tarde (en carrito o checkout).  
   **Evidencia:** evidencia_09_stock_no_visible.png  
   **Impacto:** Frustración y pedidos inválidos.

8. **ID: H11-C**  
   **Heurística:** H1 - Visibilidad del estado del sistema  
   **Pantalla:** Checkout – Confirmación de dirección  
   **Descripción:** No feedback claro si dirección es inválida o fuera de zona de entrega, permitiendo avanzar y fallar tarde.  
   **Evidencia:** evidencia_20_direccion_no_feedback.png  
   **Impacto:** Error tardío en flujo crítico.

### Severidad 2 y 1 (Menor / cosmético)
9. **ID: H3-A** – H7 – Flexibilidad y eficiencia (2)  
10. **ID: H6-B** – H6 – Reconocimiento antes que recuerdo (1)  
11. **ID: H10-C** – H10 – Ayuda y documentación (2)  
12. **ID: H12-B** – H4 – Consistencia y estándares (3)  

## Recomendaciones Accionables (priorizadas)
1. **Alta prioridad (severidad 4)**: Reducir banners en home a máximo 3-4, usar carrusel controlado por usuario, aumentar whitespace y priorizar búsqueda sticky en parte superior (inspirado en iFood/Uber Eats).  
2. **Alta prioridad**: Unificar diseño de botones CTA (color, tamaño, tipografía) siguiendo Apple HIG para consistencia.  
3. **Prioridad media-alta**: Agregar barra de progreso + texto explicativo en pago (ej. "Confirmando restaurante...", "Procesando pago – ~10s").  
4. **Prioridad media**: Implementar botón "Cancelar pedido" directo en pantalla de confirmación (con confirmación secundaria).  
5. **Prioridad media**: Mejorar mensajes de error con diagnóstico claro y acciones inmediatas ("Reintentar", "Cambiar método de pago", "Ver soporte").  
6. **Prioridad baja-media**: Destacar "Repedir último pedido" en home y mejorar accesibilidad al centro de ayuda desde checkout.

## Conclusiones
Rappi ofrece conveniencia y adaptación local excelente, pero la sobrecarga visual (H8) y falta de consistencia (H4) sacrifican usabilidad en favor de monetización. Estas violaciones generan abandono de carrito alto y frustración en momentos críticos (checkout). Con las recomendaciones propuestas, se podría mejorar significativamente la tasa de conversión y satisfacción del usuario en iOS, alineándose mejor con estándares de Apple y expectativas del mercado colombiano.

**Referencias**
- Nielsen, J. (1994). 10 Usability Heuristics for User Interface Design. Nielsen Norman Group. https://www.nngroup.com/articles/ten-usability-heuristics/
- Apple Human Interface Guidelines. https://developer.apple.com/design/human-interface-guidelines/
- Material Design 3 (referencia cruzada para Android/iOS híbrido). https://m3.material.io/

**Anexos:** Ver carpeta /evidencias/ para todas las capturas referenciadas.
