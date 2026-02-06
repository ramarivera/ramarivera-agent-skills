# Typography

## Using type treatments in Apps SDK UI

## Scales

Scales include sizing for heading and text sizes, with combinations of `font-size`,`font-weight`, and `line-height`.

| Name | Size | Weight | Tracking | Line |
| --- | --- | --- | --- | --- |
| heading-5xl | 72px | 600 | 0em | 72px |
| heading-4xl | 60px | 600 | 0em | 60px |
| heading-3xl | 48px | 600 | 0em | 48px |
| heading-2xl | 36px | 600 | 0em | 42px |
| heading-xl | 32px | 600 | 0em | 38px |
| heading-lg | 24px | 600 | 0em | 28px |
| heading-md | 20px | 600 | 0em | 26px |
| heading-sm | 18px | 600 | 0em | 26px |
| heading-xs | 16px | 600 | 0em | 24px |
| text-lg | 18px | 400 | 0em | 29px |
| text-md | 16px | 400 | 0em | 24px |
| text-sm | 14px | 400 | 0em | 20px |
| text-xs | 12px | 400 | 0em | 18px |
| text-2xs | 10px | 400 | 0em | 14px |
| text-3xs | 8px | 400 | 0em | 12px |

All text sizes are exposed to Tailwind, with custom utilities for `heading-*` and `text-*` classes.

##### Get started

## Building your first app

Inline cards in Apps SDK UI keep copy short and actionable. Provide just enough context for the task, then pair it with a clear next step.

```
<h5 className="text-secondary mb-1">Get started</h5>
<h2 className="heading-xl mb-3">Building your first app</h2>
<p className="text-md">
  Inline cards in Apps SDK UI keep copy short and actionable. Provide just enough
  context for the task, then pair it with a clear next step.
</p>
```

The underlying CSS variables can be referenced directly in CSS, as needed.

```
/* Headings */
--font-heading-xl-size: 2rem; /* 32px  */
--font-heading-xl-line-height: 2.375rem; /* 38px */
--font-heading-xl-weight: var(--font-weight-semibold);
/* Text */
--font-text-md-size: 1rem; /* 16px  */
--font-text-md-line-height: 1.5; /* 24px  */
--font-text-md-weight: var(--font-weight-normal);

```

## Colors

Four semantic text colors are provided by default – base, emphasis, prose, secondary, and tertiary.

text-default

text-secondary

text-tertiary

```
<p className="text-default">text-default</p>
<p className="text-secondary">text-secondary</p>
<p className="text-tertiary">text-tertiary</p>
```

For more details on using semantic color variables directly,

explore our design tokens

.

## Weights

The available weights are fairly standard. Semibold is the most common bolded value.

font-normal

font-medium

font-semibold

font-bold

```
<p className="font-normal">font-normal</p>
<p className="font-medium">font-medium</p>
<p className="font-semibold">font-semibold</p>
<p className="font-bold">font-bold</p>
```

CSS variables are exposed in the common Tailwind pattern of `font-weight-*`:

```
--font-weight-normal: 400;
--font-weight-medium: 500;
--font-weight-semibold: 600;
--font-weight-bold: 700;

```

## Line height

Line heights are optimized for readability and tailored to how each `font-size` sits on the baseline.

Values are designed to create optimal centering with `align-items: center` for that given `font-size`, which ultimately means aligning to an odd or even pixel value.

text-md

Prose

Typography is the silent art that shapes how we experience written language. Beyond mere letters, it orchestrates rhythm, hierarchy, and emotion—guiding the reader’s eye and setting the tone before a single word is read. The beauty of typography lies in its subtlety: the careful balance of space and form, the harmony between font size and line height, and the way thoughtfully chosen type can make content feel effortless, inviting, and human. When typography is done well, it disappears, letting the message shine—yet its influence is always felt, elevating both clarity and aesthetic pleasure.

Icon & text

Writing style

Hyperlink

Label

Previous

###### Responsive design

Next

###### Colors
