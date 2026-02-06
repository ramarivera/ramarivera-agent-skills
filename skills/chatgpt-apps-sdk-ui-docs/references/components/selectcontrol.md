# SelectControl

## Customizable select control for use with any type of floating UI

## Usage

```
import { SelectControl } from "@openai/apps-sdk-ui/components/SelectControl";

```

```
const [value, setValue] = useState("")
const placeholder = "Select date..."

return (
  // Use any floating UI, like <Menu>, <Popover>, etc.
  <Menu>
    <Menu.Trigger>
      <SelectControl
        selected={!!value}
        onClearClick={() => setValue("")}
        StartIcon={CalendarAlt}
      >
        {value || placeholder}
      </SelectControl>
    </Menu.Trigger>
    <Menu.Content>
      <Menu.RadioGroup value={value} onChange={setValue}>
        ...
      </Menu.RadioGroup>
    </Menu.Content>
  </Menu>
)
```

## Reference

| Name | Description | Default |
| --- | --- | --- |
| variant | Style variant for the Button<br>"soft""outline""ghost" | "outline" |
| pill | Determines if the control should be a fully rounded pill shape<br>boolean | true |
| size | Determines size of the size and spacing of the control.

| 3xs | 2xs | xs | sm | md | lg | xl | 2xl | 3xl |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| `22px` | `24px` | `26px` | `28px` | `32px` | `36px` | `40px` | `44px` | `48px` |

| block | Extends the control to 100% of available width.<br>boolean | true |
| opticallyAlign | Applies a negative margin using the current gutter to optically align the control<br>with surrounding content.<br>"start""end" | - |
| disabled | Disables the control visually and from interactions<br>boolean | false |
| invalid | Visually indicates that the control is in an invalid state<br>boolean | false |
| selected | Indicates that the control is selected. An unselected state will display placeholder styles.<br>boolean | false |
| onClearClick | Display a clear action that allows the select to be unset.<br>(() =\> void) | false |
| onInteract | Primary handler for when the control is selected with pointer or keyboard events<br>(() =\> void) | - |
| loading | Displays loading indicator on top of button contents<br>boolean | false |
| dropdownIconType | Icon displayed in the far right of the select trigger<br>"none""chevronDown""dropdown" | "dropdown" |
| StartIcon | Icon displayed at the start of the control<br>ComponentType<SVGProps<SVGSVGElement>> | - |
| ref | Ref<HTMLSpanElement \| null> | - |

```
<SelectControl>
  Select...
</SelectControl>
```
```
<SelectControl StartIcon={CalendarAlt}>
  Reader
</SelectControl>
```
```
<SelectControl dropdownIconType="dropdown">
  Select...
</SelectControl>
```
```
<SelectControl
  onClearClick={function Xs(){}}
  onInteract={function Xs(){}}
  selected
>
  Sample value
</SelectControl>
```
```
<SelectControl loading>
  Loading models...
</SelectControl>
```
```
<SelectControl invalid>
  Pineapple on pizza
</SelectControl>
```
```
<SelectControl disabled>
  Reader
</SelectControl>
```
```
<div className="w-[290px] text-center p-2 border border-dashed border-alpha/20 rounded-md">
  <SelectControl
    block
    size="lg"
  >
    Select...
  </SelectControl>
</div>
```
