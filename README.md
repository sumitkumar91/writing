# blog.sumitk.me

An academic, editorial blog by **Sumit Kumar**, built with **Astro 5**, **MDX**, **Tailwind CSS**, and **KaTeX**.

Combining three design traditions:
1. **Academic Journals**: Rigorous structure, numbered theorems and lemmas, formal proofs with Q.E.D. halmos symbols, display math, and structured bibliographic citations.
2. **Editorial Publications**: High-legibility serif typography (*Newsreader*), generous whitespace, Tufte-style sidenotes and margin notes, and a warm ivory paper palette.
3. **Personal Websites**: Clean typography, subtle personal branding, dark/light theme toggle, RSS syndication, and zero-JS reading overhead.

---

## 🚀 Quick Start

```bash
# Install dependencies (already installed)
npm install

# Start local development server
npm run dev

# Build production static site
npm run build

# Preview production build locally
npm run preview
```

---

## ✍️ Writing a New MDX Essay

Create a new file in `src/content/blog/<slug>.mdx`:

```mdx
---
title: "Your Essay Title Here"
description: "A concise 1-2 sentence overview of the argument."
pubDate: 2026-10-10
tags: ["Mathematics", "Computation"]
featured: true
author: "Sumit Kumar"
math: true
draft: false
---

<Abstract keywords={["Keyword 1", "Keyword 2"]}>
A succinct academic summary of your findings or thesis.
</Abstract>

## 1. Introduction

Your introductory prose here. You can include inline LaTeX like $E = mc^2$ or display equations:

$$
\mathcal{L}(\theta) = \mathbb{E}_{x \sim p_{\text{data}}} \left[ \log D(x) \right]
$$
```

---

## 🧩 Academic MDX Components Available

All components are automatically provided to MDX files without requiring manual imports:

### 1. Mathematical Notation
- Inline math: `$f(x) = \sigma(W x + b)$`
- Display math:
  ```latex
  $$
  \nabla_\theta J(\theta) = \mathbb{E}_{\pi_\theta} \left[ \nabla_\theta \log \pi_\theta(s, a) Q^{\pi_\theta}(s, a) \right]
  $$
  ```

### 2. Theorems, Lemmas, Definitions & Proofs
```mdx
<Definition number="1.1" term="Topological Space">
A topological space is a pair $(X, \tau)$ consisting of a set $X$ and a topology $\tau$.
</Definition>

<Theorem number="1.1" name="Fixed Point Theorem">
Let $f: [a, b] \to [a, b]$ be a continuous function. Then $f$ has at least one fixed point.
</Theorem>

<Lemma number="1.1">
Any closed subset of a compact space is compact.
</Lemma>

<Proof of="Theorem 1.1">
Define $g(x) = f(x) - x$. Since $g(a) \ge 0$ and $g(b) \le 0$, by the Intermediate Value Theorem...
</Proof>
```

### 3. Tufte-Style Sidenotes & Margin Notes
- **Sidenote (Numbered)**: Displays as a superscript reference in text. On desktop (`xl:` screens), it floats directly into the right margin beside the text. On mobile, readers can tap to expand it inline.
  ```mdx
  This is an important claim.<Sidenote id="1">Refer to Shannon (1948) for the initial derivation.</Sidenote>
  ```
- **Margin Note (Unnumbered)**:
  ```mdx
  A tangential thought or clarification.<Marginnote id="tangent-1">This applies strictly in discrete domains.</Marginnote>
  ```

### 4. Editorial Callouts
```mdx
<Callout type="insight" title="Thermodynamic Equilibrium">
The system converges to minimum free energy under uniform boundary conditions.
</Callout>
```
*Types*: `note`, `warning`, `insight`, `remark`, `quote`.

### 5. Figures with Captions
```mdx
<Figure number="1" caption="Phase portrait of the non-linear dynamical system.">
  <!-- Can contain an image or custom SVG/diagram -->
</Figure>
```

### 6. Citations & References
```mdx
According to <Cite id="shannon1948" label="Shannon (1948)" />, information entropy measures...

<References>
  <RefEntry
    id="shannon1948"
    authors="Shannon, C. E."
    year="1948"
    title="A Mathematical Theory of Communication"
    source="Bell System Technical Journal, 27(3), 379-423"
    doi="10.1002/j.1538-7305.1948.tb01338.x"
  />
</References>
```

---

## 🎨 Aesthetics & Typography

- **Paper Palette**: Warm ivory light theme (`#faf8f5`) and warm obsidian dark theme (`#141312`).
- **Body Serif**: Google Font **Newsreader** (designed specifically for continuous editorial reading).
- **UI & Metadata Sans**: **Plus Jakarta Sans**.
- **Code & Equations**: **JetBrains Mono** with KaTeX SSR.
- **Reading Aids**: Reading progress bar, interactive Table of Contents with active scrollspy, and one-click BibTeX citation copying.

---

## 🚢 Deployment

The project builds to a completely static directory (`dist/`) and can be deployed anywhere:
- **Cloudflare Pages**: Framework preset `Astro`, build command `npm run build`, output directory `dist`.
- **Vercel**: Framework preset `Astro`, build command `npm run build`.
- **GitHub Pages**: Output to `dist` using the standard GitHub Pages Astro action.
