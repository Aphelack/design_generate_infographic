---
name: AI Infographic & Visual Explainer Generator
alias: design_generate_infographic
description: Transform text, data, documents, or raw ideas into polished infographics and visual explainers. Use when you need to communicate complex information visually — statistics, processes, comparisons, timelines, or topic breakdowns.
type: tools: designer
subtype: image
tags: infographic, visual, explainer, data, design, layout, social-media
author: qcai-skills
---

## Purpose

Turn any block of text, data, research, or abstract concept into a clear, visually compelling infographic or explainer image. This skill handles layout thinking, visual hierarchy, icon logic, color selection, and generation prompt construction so the output is ready for use in presentations, social media, or reports.

## Use When

- The user has a topic, text, or dataset and wants to visualize it as an infographic
- A concept needs to be explained visually (process flow, how-it-works, comparison, ranked list, timeline)
- The output must be shareable on social media, embedded in a report, or used in a presentation
- The user wants a data-driven visual from statistics or research findings
- A step-by-step process or workflow needs to be illustrated

## Do Not Use When

- The user needs an animated or video explainer — use a motion skill instead
- The data requires interactive charts or dashboards — use a frontend/app skill
- The output is a full-page document layout (report, whitepaper) — this skill targets single-image explainers only
- The request is for a logo, icon set, or brand identity — use a dedicated branding skill

## Inputs

- **Topic or content**: raw text, a paragraph, bullet points, a URL, document excerpt, or dataset
- **Infographic type**: one of — `statistical`, `process/steps`, `comparison`, `timeline`, `list/ranking`, `concept explainer`, `how it works`
- **Target format**: aspect ratio and intended use (e.g., `16:9` for presentations, `4:5` for Instagram, `1:1` for square post, `A4 portrait` for reports)
- **Color direction**: brand colors (hex codes), a mood (e.g., "professional blue", "warm and friendly"), or "auto"
- **Style**: `flat illustration`, `minimal line art`, `bold editorial`, `data-driven corporate`, `friendly and educational`
- **Audience**: who will read this (developers, executives, general public, students, etc.)

## Rules

1. **Always define the infographic type first** before generating — the layout logic differs per type (steps use vertical flow; comparisons use side-by-side; timelines use horizontal or diagonal tracks; rankings use bar-like hierarchy).
2. **Limit information density** — a single infographic should convey 3–7 key ideas maximum. If the input has more, split into multiple frames or ask which 5 to prioritize.
3. **Visual hierarchy is non-negotiable** — headline → subheadings → data/icons → captions. Never make all text the same visual weight.
4. **Color restraint** — use 1 primary accent + 1 secondary + neutrals. Never exceed 4 distinct hues in a single infographic unless it is a categorical data chart.
5. **Icons must support the content**, not decorate it. Each icon should map directly to the concept it accompanies.
6. **Text inside the image must be minimal** — if a label needs more than 6 words, rephrase or break it up.
7. **Always match the output to the intended platform** — social media sizes differ from report embeds. Set the correct aspect ratio before generation.
8. **Accessibility**: ensure text-on-background contrast is WCAG AA compliant. Avoid red/green-only distinctions for data encoding.

## Workflow

1. **Parse the input** — extract key facts, concepts, or data points from the provided content. Identify the 5–7 most important ideas.
2. **Select the infographic type** — match the content structure to the appropriate layout type:
   - Numbered steps or process → `process/steps`
   - A vs B → `comparison`
   - Statistics and percentages → `statistical`
   - Events ordered in time → `timeline`
   - Best-of or ranked items → `list/ranking`
   - Explaining a concept → `concept explainer` or `how it works`
3. **Design the layout in words** — describe the visual structure before generating:
   - Number of sections / cards
   - Flow direction (top-down, left-right, circular)
   - Key headline and supporting labels
   - Where icons or data visualizations go
4. **Choose the color system** — if brand colors are provided, anchor the palette there. Otherwise derive from the topic mood (e.g., health = green + white, finance = navy + gold, tech = dark + electric blue). Apply the 1 accent + 1 secondary + neutrals rule.
5. **Select typography style** — bold sans-serif for headlines, regular sans-serif for body labels. Specify font weight ratios (e.g., headline 700, sublabel 400).
6. **Build the generation prompt** — write a precise, detailed image generation prompt using the Prompt Engineering Guide below.
7. **Generate the infographic** using the image generation tool with the constructed prompt.
8. **Review the output** against the Validation checklist.
9. **Deliver** the image + prompt + iteration suggestions to the user.

## Prompt Engineering Guide

A strong infographic generation prompt follows this pattern:

```
[Style keyword] infographic on "[TOPIC]".
Layout: [describe sections, flow, and structure].
Color palette: [primary hex] primary, [secondary hex] secondary, [background] background, white text.
Typography: bold sans-serif headline "[HEADLINE TEXT]", clean labels for each section.
Sections: [list each section with its label and what visual/icon it uses].
Icons: flat [style] icons for each section.
Format: [W]×[H]px, [aspect ratio], no border, clean background, professional finish.
No watermarks, no lorem ipsum, all text is real and legible.
```

**Adapt by type:**

- **Process/Steps**: add `numbered steps flowing top to bottom with connecting arrows`
- **Comparison**: add `two-column side-by-side layout, left = [A], right = [B], header row highlights key difference`
- **Statistical**: add `large bold percentage callouts, subtle bar or donut chart accents`
- **Timeline**: add `horizontal timeline track with milestone markers, dates above, descriptions below`
- **List/Ranking**: add `vertical ranked list with position numbers, bar-length proportional to rank value`

## Validation

- [ ] The infographic type was explicitly chosen before generation
- [ ] Information is limited to 3–7 key ideas — no overloaded layout
- [ ] Visual hierarchy is clear: headline dominates, labels are secondary, captions are tertiary
- [ ] Color palette uses ≤4 distinct hues
- [ ] Icons are semantically relevant, not decorative
- [ ] All text inside the image is real, legible, and under 6 words per label
- [ ] Aspect ratio matches the intended platform
- [ ] Contrast is sufficient (WCAG AA minimum)
- [ ] The generation prompt is included in the output so the user can iterate

## Output

Deliver:

1. **Generated infographic image** — produced via the image generation tool using the constructed prompt
2. **Generation prompt used** — full text, so the user can refine and re-run
3. **Layout rationale** — 2–4 sentences explaining the type chosen and structure decisions
4. **Iteration suggestions** — 2–3 ways the user could vary the output (different style, color, or layout)