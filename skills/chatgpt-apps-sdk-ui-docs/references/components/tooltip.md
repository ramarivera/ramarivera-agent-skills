# Tooltip

## Brief and informative hover text

## Usage

```
import { Tooltip } from "@openai/apps-sdk-ui/components/Tooltip";

```

```
<Tooltip
  content="This is additional context that appears when the trigger is hovered or focused"
>
  <Tooltip.TriggerDecorator>
    Simple text with tooltip
  </Tooltip.TriggerDecorator>
</Tooltip>
```

## Reference

| Name | Description | Default |
| --- | --- | --- |
| content\* | The content of the tooltip. If `null`, the tooltip will not render.<br>ReactNode | - |
| compact | Short, 1-3 word tooltips, stylized inversely from normal tooltips<br>boolean | false |
| interactive | Indicates that the tooltip has interactive content, and should remain open when hovered.<br>boolean | - |
| maxWidth | Defines the `max-width` of the tooltip content. `"none"` creates a single-line, naturally sized tooltip.<br>number"none" | 300 |
| forceOpen | Forces the tooltip to remain open or closed<br>boolean | - |
| openDelay | Delay of when the tooltip is shown from first interaction, in milliseconds.<br>number | 150 |
| preventUnintentionalClickToClose | Prevents the tooltip from closing when the trigger is clicked right after opening<br>true | false |
| align | The preferred alignment against the trigger. May change when collisions occur.<br>"start""end""center" | "center" |
| alignOffset | An offset in pixels from the "start" or "end" alignment options.<br>number | 0 |
| side | The preferred side of the trigger to render against when open. Will be reversed when collisions occur.<br>"top""right""bottom""left" | "top" |
| sideOffset | The distance in pixels from the trigger.<br>number | 5 |
| gutterSize | Gutter sizing inside the tooltip content<br>"sm""md""lg" | "md" |
| ref | Ref for the tooltip<br>Ref<HTMLDivElement \| null> | - |
| onPointerDown | PointerEventHandler | - |
| onClick | MouseEventHandler | - |
| contentClassName | Optional class name to apply to the tooltip content<br>string | - |

```
<div className="flex items-center gap-4">
  <Tooltip
    content="This is additional context that appears when the trigger is hovered or focused"
  >
    <Button
      color="primary"
      size="lg"
    >
      Sample button
    </Button>
  </Tooltip>
  <Tooltip
    content="This is additional context that appears when the trigger is hovered or focused"
  >
    <span>
      Inaccessible trigger
    </span>
  </Tooltip>
</div>
```
```
<Tooltip
  content={disabled ? "This action is disabled for reasons" : null}
>
  <Button color="primary" size="lg" disabled={disabled}>
    Sample button
  </Button>
</Tooltip>
```
