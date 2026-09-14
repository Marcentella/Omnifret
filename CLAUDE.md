# CLAUDE.md — PlainChord

## Qué es
App web gratuita de aprendizaje visual de guitarra. Centraliza en una pantalla lo que hoy está disperso: diagramas de acordes, notación técnica de tablatura, dificultad de transición entre acordes.

## Filosofía de producto (no negociable)
Referencia objetiva tipo wiki. **No** adaptativo/gamificado tipo Duolingo. La dificultad de una transición es una propiedad fija de esa transición, no algo personalizado por usuario. Sin progreso individual rastreado.

## Stack
- Next.js (React + TypeScript) + Tailwind CSS
- Datos: JSON estructurado, sin base de datos externa
- Hosting: Vercel
- Audio: Meyda + Web Audio API (procesado 100% client-side, nunca en servidor)
- Persistencia local: IndexedDB (no localStorage — límite de tamaño insuficiente)

## Regla legal central — aplica a toda feature nueva
PlainChord no aloja, indexa, ni facilita la obtención de contenido con copyright (tablaturas de canciones). El usuario importa su propio contenido; PlainChord solo lo visualiza. Nunca compartido entre usuarios, nunca hosteado con fines de distribución. Ver skill `no-hosting-rule` y FEATURES.md para el razonamiento legal completo.

## Alcance MVP
- Biblioteca de acordes (diagramas generados desde datos)
- Glosario de notación técnica (definición + ejecución física, no solo teoría)
- Sistema de dificultad de transiciones
- Import de tabs: texto plano (Fase 1), Guitar Pro vía alphaTab como parser (Fase 2)
- Un solo renderer propio de tabs, sin importar la fuente de datos
- Freemium: gratis = todo lo anterior; premium = "próximamente", sin cobro real todavía

## Explícitamente fuera de alcance (no implementar sin discutirlo primero)
- Cuentas de usuario obligatorias
- Procesamiento real de pagos
- Personalización/adaptación por usuario
- Guía de tono/amplificador
- Import por OCR/screenshot
- Cálculo automático de digitación (I+D, no escopeado aún)
- Sync entre dispositivos / cloud storage (requiere revisión legal antes de construir)

## Convenciones de arquitectura a respetar
- Reusar el generador de diagramas de la biblioteca de acordes para digitación en tabs — no duplicar.
- Todo import (texto plano o Guitar Pro) converge en el mismo formato de datos interno antes de llegar al renderer.
- Construir por Fases/Pasos, uno a la vez — no implementar varias fases en una sola sesión. Ver FEATURES.md para el desglose.
- Usar `lucide-react` para íconos de interfaz, no emoji — el renderizado de emoji varía entre sistemas operativos y navegadores; lucide-react da un ícono consistente en cualquier plataforma.

## Archivos de referencia
- `FEATURES.md` — historial de decisiones de features, razonamiento, roadmap por fases (no cargar completo cada vez, consultar cuando sea relevante).
- `.claude/skills/no-hosting-rule/` — regla legal como skill invocable.
