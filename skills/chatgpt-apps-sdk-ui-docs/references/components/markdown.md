# Markdown

## Render rich formatted content

## Usage

```
import { Markdown } from "@openai/apps-sdk-ui/components/Markdown"

```

### Headers

# Heading 1

## Heading 2

### Heading 3

#### Heading 4

##### Heading 5

###### Heading 6

* * *

### Text samples

Emphasis, aka italics, with _asterisks_ or _underscores_.

Strong emphasis, aka bold, with **asterisks** or **underscores**.

Combined emphasis with **asterisks and _underscores_**.

Strikethrough uses two tildes. ~~Scratch this.~~

* * *

### Lists

#### Unordered List

- Item 1
- Item 2
  - Nested Item 1
  - Nested Item 2

#### Ordered List

1. First item
2. Second item
1. Subitem 1
2. Subitem 2

Sample paragraph breaking up multiple `<ol>`.

3. Third item
1. Subitem 1
2. Subitem 2
4. Fourth item

#### Poorly formatted

01. Item 1
02. Item 2
03. Item 3
04. Item 4
05. Item 5
10. Item 10
11. Item 11

* * *

### Blockquote

> This is a blockquote.
>
> It can span multiple lines and include other elements like lists or even code.

* * *

## Table

| ID | Title | Owner | Updated | Progress |
| --- | --- | --- | --- | --- |
| UX-17 | Notebook typography polish | Tyler | 2025-09-07 | 65% |
| API-24 | Realtime auth fallback | David | 2025-09-05 | 30% |
| MD-09 | Markdown emoji coverage | Jane | 2025-09-06 | 95% |
| ACC-12 | Keyboard trap audit | Priya | 2025-09-04 | 80% |
| DOC-11 | Design token glossary | Jonah | 2025-09-02 | 45% |
| INF-15 | Bundle size smoke tests | Elise | 2025-09-01 | 25% |

## Links

Here is a [sample link](https://www.example.com/).

## Inline Code

Here is some inline code: `var x = 10;`

## Nested Elements

> ### Nested Blockquote with Code Block
>
> ```python
> # Code inside a blockquote
> print("Hello from blockquote code block")
> ```

```
<Markdown>{markdownContent}</Markdown>
```

## Reference

| Name | Description | Default |
| --- | --- | --- |
| directives | MarkdownDirective<any>\[\] | - |
| includeMath | Determines if remark-math plugins should be loaded for rendering LaTeX<br>boolean | false |
| breakNewLines | Determines whether single newlines should insert <br>tags<br>boolean | false |
| components | Record<string, MarkdownComponent> | - |
| remarkPlugins | PluggableListnull | - |
| rehypePlugins | PluggableListnull | - |
| allowedElements | readonly string\[\] \| null | - |
| disallowedElements | readonly string\[\] \| null | - |
| urlTransform | UrlTransformnull | (url: string) => {<br> if (url.startsWith("tel:") \|\| url.startsWith("sms:")) {<br> return url<br> }<br> return reactMarkdownDefaultUrlTransform(url)<br>} |
| skipHtml | boolean | - |
| className | string | - |
| copyableCodeBlocks | boolean | true |
| children | - | - |

## Math

Use `includeMath` to enable LaTeX rendering.

#### Display integral

∫0∞e−xdx=1\\int\_{0}^{\\infty} e^{-x} \\, dx = 1∫0∞​e−xdx=1

#### Basel problem

∑n=1∞1n2=π26\\sum\_{n=1}^{\\infty} \\frac{1}{n^2} = \\frac{\\pi^2}{6}n=1∑∞​n21​=6π2​

#### Matrix (bmatrix)

\[1234\]\\begin{bmatrix}
1 & 2 \\\
3 & 4
\\end{bmatrix}\[13​24​\]

#### Piecewise (cases)

f(x)={x2x≥0−xx<0f(x) = \\begin{cases}
x^2 & x \\ge 0 \\\
-x & x < 0
\\end{cases}f(x)={x2−x​x≥0x<0​

```
<Markdown includeMath>{markdownWithLatex}</Markdown>
```
