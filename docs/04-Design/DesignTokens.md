# Design Tokens

## Objetivo

Este documento define os Design Tokens da plataforma PetCare.

Design Tokens são valores reutilizáveis que representam decisões de design, como cores, tipografia, espaçamentos e animações. Eles funcionam como uma fonte única de verdade para designers e desenvolvedores, garantindo consistência entre protótipos e implementação.

Os tokens devem ser consumidos pelos componentes da interface, evitando valores fixos diretamente no código.

---

# Estrutura

Os tokens estão organizados nas seguintes categorias:

- Colors
- Typography
- Spacing
- Border Radius
- Borders
- Shadows
- Opacity
- Motion
- Breakpoints
- Z-Index
- Focus
- Iconography

---

# Colors

As cores são definidas por função, e não por aparência.

## Brand

- color.brand.primary
- color.brand.secondary
- color.brand.accent

---

## Surface

- color.surface.primary
- color.surface.secondary
- color.surface.tertiary

---

## Background

- color.background.primary
- color.background.secondary

---

## Text

- color.text.primary
- color.text.secondary
- color.text.disabled
- color.text.inverse

---

## Border

- color.border.default
- color.border.focus
- color.border.disabled

---

## Feedback

### Success

- color.success.background
- color.success.text
- color.success.border

### Warning

- color.warning.background
- color.warning.text
- color.warning.border

### Error

- color.error.background
- color.error.text
- color.error.border

### Info

- color.info.background
- color.info.text
- color.info.border

---

# Typography

## Font Family

- font.family.primary
- font.family.monospace

---

## Font Weight

- font.weight.light
- font.weight.regular
- font.weight.medium
- font.weight.semibold
- font.weight.bold

---

## Font Size

- font.size.xs
- font.size.sm
- font.size.md
- font.size.lg
- font.size.xl
- font.size.2xl
- font.size.3xl

---

## Line Height

- line.height.tight
- line.height.normal
- line.height.relaxed

---

# Spacing

A escala de espaçamento segue uma base de 8 pixels.

- spacing.0
- spacing.1
- spacing.2
- spacing.3
- spacing.4
- spacing.5
- spacing.6
- spacing.8
- spacing.10
- spacing.12
- spacing.16

---

# Border Radius

- radius.none
- radius.sm
- radius.md
- radius.lg
- radius.xl
- radius.full

---

# Borders

- border.width.none
- border.width.thin
- border.width.medium
- border.width.thick

---

# Shadows

- shadow.none
- shadow.sm
- shadow.md
- shadow.lg
- shadow.xl

---

# Opacity

- opacity.disabled
- opacity.overlay
- opacity.hover

---

# Motion

## Duration

- motion.duration.fast
- motion.duration.normal
- motion.duration.slow

---

## Easing

- motion.easing.default
- motion.easing.enter
- motion.easing.exit

---

# Breakpoints

- breakpoint.mobile
- breakpoint.tablet
- breakpoint.desktop
- breakpoint.wide

---

# Z-Index

- z.base
- z.dropdown
- z.sticky
- z.modal
- z.toast
- z.tooltip

---

# Focus

Tokens específicos para acessibilidade.

- focus.outline.width
- focus.outline.offset
- focus.outline.color

---

# Iconography

- icon.size.sm
- icon.size.md
- icon.size.lg
- icon.size.xl

---

# Utilização

Os componentes da aplicação devem consumir apenas Design Tokens.

Exemplo:

✔ Utilizar

color.text.primary

✘ Evitar

#212121

---

# Versionamento

Qualquer alteração em um token deve ser considerada uma mudança global e avaliada quanto ao impacto em todos os componentes da aplicação.

---

# Relação com outros documentos

Este documento complementa:

- DesignSystem.md
- Components.md
- Layouts.md

Todos os componentes devem utilizar exclusivamente os tokens definidos neste documento.
