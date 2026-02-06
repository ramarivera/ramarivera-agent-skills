# Input

## Semantic input text collection

## Usage

```
import { Input } from "@openai/apps-sdk-ui/components/Input";

<Input
  placeholder="Enter text..."
/>
```

## Reference

| Name | Description | Default |
| --- | --- | --- |
| placeholder | string | - |
| allowAutofillExtensions | Allow autofill extensions to appear in the input<br>boolean | false |
| disabled | Disables the select visually and from interactions<br>boolean | false |
| invalid | Mark the input as invalid<br>boolean | false |
| variant | Visual style of the input<br>"soft""outline" | "outline" |
| size | Controls the size of the input

| 3xs | 2xs | xs | sm | md | lg | xl | 2xl | 3xl |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| `22px` | `24px` | `26px` | `28px` | `32px` | `36px` | `40px` | `44px` | `48px` |

| gutterSize | Controls gutter on the edges of the input, defaults to value from `size`.

| 2xs | xs | sm | md | lg | xl |
| --- | --- | --- | --- | --- | --- |
| `6px` | `8px` | `10px` | `12px` | `14px` | `16px` |

| autoSelect | Select all contents of the input when mounted.<br>boolean | false |
| onAutofill | Callback invoked when the input is autofilled by the browser<br>(() =\> void) | - |
| startAdornment | Content rendered at the start of the input<br>ReactNode | - |
| endAdornment | Content rendered at the end of the input<br>ReactNode | - |
| pill | Determines if the button should be a fully rounded pill shape<br>boolean | false |
| opticallyAlign | Applies a negative margin using the current gutter to optically align the input<br>with surrounding content.<br>"start""end" | - |

```
<Input
  placeholder="Start adornment"
  startAdornment={<Search className="fill-tertiary" />}
/>
```
```
<Input
  placeholder="Enter text..."
  value={value}
  onChange={(evt) => setValue(evt.target.value)}
  pill
  endAdornment={
    value ? (
      <Button
        className="-mr-2.5"
        color="secondary"
        variant="soft"
        uniform
        size="3xs"
        onClick={() => setValue("")}
        pill
      >
        <X />
      </Button>
    ) : undefined
  }
/>
```
```
<Input
  defaultValue="Jane Doe"
  disabled
  placeholder="Enter text..."
/>
```
```
<Input
  invalid
  placeholder="Invalid input"
/>
```
```
<Input
  defaultValue="Toggle to auto select"
  placeholder="Add text..."
/>
```
```
<Input
  key="true"
  allowAutofillExtensions
  name="email"
  placeholder="Allowed"
/>
```
```
<div className="flex gap-2">
  <Input
    placeholder="jane.doe@gmail.com"
    size="lg"
    variant="outline"
  />
  <Button
    color="primary"
    size="lg"
    variant="outline"
  >
    Subscribe
  </Button>
</div>
```
