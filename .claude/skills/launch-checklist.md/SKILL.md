---
name: launch-checklist
description: Usar SIEMPRE antes de dar por terminada una feature que sea visible al usuario final, recolecte datos, muestre contenido embebido de terceros, o esté cerca de un lanzamiento/entrega.
---

Checklist de consideraciones legales/accesibilidad filtrado específicamente para el
alcance real de PlainChord — no es una lista genérica, cada ítem está evaluado contra
lo que este proyecto realmente hace.

## Aplica ahora (revisar en cada feature relevante)

- **Contraste de color**: la app usa colores para transmitir significado (dificultad
  fácil/media/difícil) — no depender solo del color, verificar contraste suficiente
  y considerar un indicador adicional (texto, ícono) para quienes no distinguen bien
  los colores.
- **Texto alternativo en imágenes**: diagramas de acordes, íconos, cualquier ilustración
  necesita alt text descriptivo, no genérico ("diagrama de digitación de Sol", no "imagen").
- **Accesibilidad general**: navegación por teclado, foco visible, tamaños de texto
  legibles — la app se presenta como una referencia tipo wiki, debe ser usable por
  cualquiera.
- **Etiquetas de botones claras**: nunca "Enviar" o "Ok" genérico si hay una acción más
  específica que nombrar ("Mostrar digitaciones", no "Buscar").
- **Formularios accesibles por teclado**: cualquier input (búsqueda de acordes, glosario,
  importar tab) debe funcionar completo sin mouse.
- **Copyright en imágenes/íconos**: cualquier ícono o ilustración usada en la UI debe
  tener licencia clara para uso en un producto (no bajar un ícono cualquiera de Google
  Images). Esto es además del tema de tablaturas ya cubierto en `no-hosting-rule`.
- **Solo recolectar datos necesarios**: ya es la filosofía del proyecto (sin cuentas
  obligatorias, sin datos de más) — cualquier feature nueva debe justificar
  explícitamente qué dato nuevo recolecta y por qué, antes de agregarlo.
- **Consentimiento en formularios**: cualquier input que recolecte un dato personal
  (por ejemplo, el botón "Avisarme" del plan premium capturando un correo) necesita
  dejar claro para qué se usará ese dato, no solo capturarlo silenciosamente.
- **Evitar afirmaciones no sustentadas**: no afirmar precisión, exactitud o resultados
  que no se han validado — especialmente relevante para el componente de detección de
  acordes por audio (I+D, exploratorio) y cualquier futuro cálculo de digitación. Usar
  lenguaje honesto ("en desarrollo", "exploratorio") en vez de vender certeza que no existe.
- **Revisar embebidos de terceros**: cualquier integración externa visible al usuario
  (YouTube IFrame para sync de video, Google Sign-In si se implementa) debe revisarse
  por sus propios términos de uso antes de integrarse.
- **Páginas reales de Términos de Servicio y Política de Privacidad**: ya redactadas
  (ver archivos separados), pero deben existir como páginas reales dentro de la app
  (rutas visibles, enlazadas desde el footer), no solo como documentos sueltos.
- **Revisar leyes locales**: el proyecto opera bajo jurisdicción chilena — cualquier
  decisión legal más allá del razonamiento ya documentado (ver FEATURES.md) debería
  confirmarse con marco legal chileno específico si el proyecto crece más allá de
  alcance académico.

## Aplica solo si se agrega la feature correspondiente (no aplica todavía)

- **Política de cookies / aviso de cookies / tracking**: no aplica mientras PlainChord no
  use cookies de terceros ni analítica de comportamiento. Si se agrega analítica
  (incluso "anónima"), revisar estos tres ítems juntos antes de lanzar esa feature.
- **Detalles reales de negocio** (razón social, dirección, etc.): baja prioridad para
  un proyecto académico individual; revisar si esto alguna vez se convierte en un
  producto con pagos reales.

## No aplica a PlainChord (y por qué)

- **Política de reembolsos**: no hay procesamiento de pagos real todavía (premium
  está marcado "próximamente"). Revisar esto recién cuando exista cobro real.
- **Eliminar reseñas falsas**: PlainChord no tiene sistema de reseñas o testimonios de
  usuarios.
