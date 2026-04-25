# AI Coding Assistant Instructions - aulasHTML

## Project Overview
**aulasHTML** is a Portuguese-language HTML/CSS learning project organized as a progressive curriculum covering web development fundamentals. This is an **educational codebase** with minimal complexity—no build tools, frameworks, or backend services.

### Project Structure
- `aula01/` — HTML semantic structure & form elements
- `aula02/` & `aula03/` — Reserved for future lessons
- `aula04/landingPage/` — Complete landing page project (EduTrack platform)

---

## Key Development Patterns

### 1. **CSS Architecture: Custom Properties & Design Tokens**
The project uses **CSS variables (custom properties)** extensively in `:root` for maintainability:

```css
:root {
    --cor-primaria: #004AC6;           /* Primary brand color */
    --espaço-lg: 2rem;                 /* Spacing scale */
    --raio-md: 0.75rem;                /* Border radius system */
    --fonte-principal: 'Segoe UI', ...;
}
```

**Pattern**: Define all design tokens once in `:root`, reference via `var()` throughout. Updates to spacing, colors, or typography require changes in only one place.

### 2. **Naming Conventions**
- **Class naming**: Portuguese kebab-case, semantic (e.g., `navbar-logo`, `hero-titulo`, `pilar-icone`)
- **HTML form fields**: camelCase IDs/names (e.g., `nomecompleto`, `dataNascimento`)
- **CSS classes**: Prefix with component name (e.g., `.navbar-*`, `.hero-*`, `.btn-*`)
- **Variable names**: Portuguese descriptive names (e.g., `--cor-fundo` for background color)

### 3. **Layout Patterns**
- **Navbar**: Fixed positioning with `backdrop-filter: blur()` for frosted glass effect
- **Hero Section**: Full viewport height (`min-height: 100vh`) with flexbox centering
- **Grid Systems**: Multi-column layouts using CSS Grid (e.g., `.sobre .container`)
- **Responsive Typography**: Uses `clamp()` function for fluid font sizing

Example from `aula04/landingPage/style.css`:
```css
.hero-titulo {
    font-size: clamp(2.5rem, 5.7rem, 4.5rem); /* min, ideal, max */
    max-width: 56rem;
}
```

### 4. **Component-Based Styling**
Style components holistically (navbar, hero, buttons) rather than utility-first. Each component includes:
- **Base styles** (structure, layout)
- **Hover/interactive states** (transitions, transforms)
- **Responsive considerations** (flex-wrap, grid adjustments)

---

## HTML Standards & Semantics

### Document Structure
All files follow Portuguese HTML5 standards:
- Language attribute: `<html lang="pt-br">`
- UTF-8 charset declaration
- Viewport meta tag for responsiveness
- Semantic HTML5 elements (`<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<aside>`, `<footer>`)

### Form Standards (from `aula01/form.html`)
- Form fields wrapped in `<div>` containers for styling
- `<label>` elements with `for` attribute linking to input `id`
- Input types: `text`, `email`, `password`, `tel`, `date`, `file`
- Textarea for multi-line text
- Select/option for dropdowns
- `required` attribute for validation
- `fieldset` for logical grouping

---

## File Organization & Development Workflow

### When Modifying `aula04/landingPage/`
1. **Update CSS in `style.css`** — All styling is centralized; no inline styles
2. **Maintain semantic HTML in `index.html`** — Comments mark major sections
3. **Keep classes isolated to components** — Avoid global overrides

### Testing/Preview
This is a **static HTML/CSS project** — preview in any browser by opening `index.html` directly. No build step, no dependencies, no server required.

### Naming Consistency
When adding new sections/components:
- Create `.component-name-part` classes following existing pattern
- Add new color/spacing variables to `:root` if needed
- Document intent with HTML comments for complex layouts

---

## Common Tasks & Patterns

### Adding a New Color
Add to `:root` (semantic naming), then reference throughout:
```css
:root {
    --cor-destaque: #FF6B35; /* New highlight color */
}

.elemento { color: var(--cor-destaque); }
```

### Creating a Button Variant
Base button style + modifier class pattern:
```css
.navbar-button { /* base */ }
.navbar-button:hover { /* interaction */ }
.btn-saiba-mais { /* variant */ }
```

### Responsive Typography
Use `clamp()` instead of media queries for font size:
```css
font-size: clamp(0.875rem, 2vw, 1.5rem); /* min, ideal, max */
```

---

## Language & Conventions
- **All code is in Portuguese**: Comments, class names, variable names, HTML structure
- **Files use `.html` and `.css` extensions only** — No JavaScript or preprocessors
- **Comments use Portuguese**: Inline explanations help learners understand intent

---

## Key Files to Reference
- `aula04/landingPage/style.css` — Complete CSS pattern examples (navbar, hero, grid layouts)
- `aula04/landingPage/index.html` — Semantic HTML structure with component organization
- `aula01/estrutura.html` — HTML semantic template reference
- `aula01/form.html` — Form field patterns and accessibility practices
