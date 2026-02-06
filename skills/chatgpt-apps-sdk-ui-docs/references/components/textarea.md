# Textarea

## Semantic multi-line text input collection

## Usage

```
import { Textarea } from "@openai/apps-sdk-ui/components/Textarea";

<div className="w-[400px]">
  <Textarea
    autoResize
    placeholder="Enter text..."
    rows={3}
  />
</div>
```

## Reference

| Name | Description | Default |
| --- | --- | --- |
| placeholder | string | - |
| allowAutofillExtensions | Allow autofill extensions to appear in the textarea<br>boolean | false |
| disabled | Disables the textarea visually and from interactions<br>boolean | false |
| invalid | Mark the textarea as invalid<br>boolean | false |
| rows | Default number of rows to display<br>number | 3 |
| autoResize | Automatically adjust the height of the textarea based on its contents.<br>boolean | false |
| variant | Visual style of the textarea<br>"soft""outline" | "outline" |
| size | Controls the size of the textarea

| 3xs | 2xs | xs | sm | md | lg | xl | 2xl | 3xl |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| `22px` | `24px` | `26px` | `28px` | `32px` | `36px` | `40px` | `44px` | `48px` |

| gutterSize | Controls gutter on the edges of the textarea, defaults to value from `size`.

| 2xs | xs | sm | md | lg | xl |
| --- | --- | --- | --- | --- | --- |
| `6px` | `8px` | `10px` | `12px` | `14px` | `16px` |

| autoSelect | Select all contents of the textarea when mounted.<br>boolean | false |
| onAutofill | Callback invoked when the textarea is autofilled by the browser<br>(() =\> void) | - |
| maxRows | Maximum number of rows that can be displayed when autoResize is enabled.<br>number | Math.max(rows, 10) |

```
<div className="w-[400px]">
  <Textarea
    autoResize
    maxRows={8}
    onChange={function Xs(){}}
    placeholder="Type to grow..."
    rows={3}
    value="Line 1
Line 2
Line 3"
  />
</div>
```
```
<div className="w-[400px]">
  <Textarea
    defaultValue="Jane Doe"
    disabled
    placeholder="Enter text..."
    rows={3}
  />
</div>
```
```
<div className="w-[400px]">
  <Textarea
    invalid
    placeholder="Invalid textarea"
    rows={3}
  />
</div>
```
```
<div className="w-[400px]">
  <Textarea
    defaultValue="Toggle to auto select"
    placeholder="Enter text..."
    rows={3}
  />
</div>
```
```
<div className="w-[400px]">
  <Textarea
    allowAutofillExtensions
    name="email"
    placeholder="Allowed"
    rows={3}
  />
</div>
```
