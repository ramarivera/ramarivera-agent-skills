# Button

## Create actions in many different styles

## Usage

```
import { Button } from "@openai/apps-sdk-ui/components/Button";

```

```
<Button
  color="primary"
  size="md"
  variant="solid"
>
  Submit
</Button>
```

## Reference

| Name | Description | Default |
| --- | --- | --- |
| children | Content rendered inside of the Button<br>ReactNode | - |
| variant | Style variant for the Button<br>"soft""solid""outline""ghost" | "\\"solid\\"" |
| color | Color for the button<br>"primary""secondary""success""info""discovery""danger""warning""caution" | "secondary" |
| size | Controls size of the button, specifically height, but also includes defaults for `gutterSize`, `iconSize`, `font-size`, etc.

| 3xs | 2xs | xs | sm | md | lg | xl | 2xl | 3xl |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| `22px` | `24px` | `26px` | `28px` | `32px` | `36px` | `40px` | `44px` | `48px` |

| pill | Determines if the button should be a fully rounded pill shape<br>boolean | true |
| disabled | Disables the button visually and from interactions<br>boolean | false |
| disabledTone | Controls the visual tone when the button is disabled. "relaxed" will use a default cursor instead of not-allowed.<br>"relaxed" | - |
| block | Determines if the button should take up 100% of available width<br>boolean | false |
| opticallyAlign | Applies a negative margin using the current gutter to optically align the button<br>with surrounding content.<br>"start""end" | - |
| iconSize | Controls the size of icons within the button, defaults to value from `size`.

| xs | sm | md | lg | xl | 2xl |
| --- | --- | --- | --- | --- | --- |
| `14px` | `16px` | `18px` | `20px` | `22px` | `24px` |

| gutterSize | Controls gutter on the edges of the button, defaults to value from `size`.

| 3xs | 2xs | xs | sm | md | lg | xl |
| --- | --- | --- | --- | --- | --- | --- |
| `4px` | `6px` | `8px` | `10px` | `12px` | `14px` | `16px` |

| className | Custom class applied to the Button element<br>string | - |
| uniform | Determines if the button should have matching width and height, based on the `size`.<br>boolean | false |
| selected | Displays selected styles on the button, varying by \`variant<br>boolean | false |
| loading | Displays loading indicator on top of button contents<br>boolean | false |
| inert | Determines whether the button should be made inert, without introducing visual change.<br>boolean | false |
| ref | Ref for the button<br>Ref<HTMLButtonElement \| null> | - |

```
<Button
  color="secondary"
  size="lg"
  uniform
  variant="ghost"
>
  <PlusLg />
</Button>
```
```
<div className="w-[290px] text-center p-2 border border-dashed border-alpha/20 rounded-md">
  <Button
    block
    size="lg"
  >
    Continue
  </Button>
</div>
```
```
<Button
  disabled
  onClick={function Xs(){}}
>
  Submit
</Button>
```
```
<Button
  inert
  onClick={function Xs(){}}
>
  Submit
</Button>
```
```
<Button loading {...restProps} />
```
```
<Button selected {...restProps} />
```
