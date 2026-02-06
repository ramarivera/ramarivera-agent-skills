# Popover

## Generic floating UI utility for contextual actions

## Usage

```
import { Popover } from "@openai/apps-sdk-ui/components/Popover";

```

```
() => <Popover>
    <Popover.Trigger>
      <Button color="primary">Generate</Button>
    </Popover.Trigger>
    <Popover.Content side="right">
      <Textarea />
      <ActionBar />
    </Popover.Content>
  </Popover>
```

## Reference

### `Popover`

| Name | Description | Default |
| --- | --- | --- |
| open | Sets controlled visibility state<br>boolean | - |
| onOpenChange | Callback invoked when visibility state changes<br>((nextState: boolean) => void) | - |
| showOnHover | boolean | false |
| hoverOpenDelay | number | 150 |

### `Popover.Trigger`

Renders the element that toggles the popover. The trigger should be the user's point of interaction for revealing the popup.

### `Popover.Content`

| Name | Description | Default |
| --- | --- | --- |
| avoidCollisions | Whether to avoid collisions with vieport/scroll containersw.<br>boolean | true |
| width | Set the `width` of the popover, in pixels.<br>number"auto" | auto |
| minWidth | Set the `min-width` of the popover, in pixels.<br>number"auto" | 300 |
| maxWidth | Set the `max-width` of the popover, in pixels.<br>number | - |
| side | The preferred side of the trigger to render against when open. Will be reversed when collisions occur.<br>"top""right""bottom""left" | "bottom" |
| sideOffset | The distance in pixels from the trigger.<br>number | 8 |
| align | The preferred alignment against the trigger. May change when collisions occur.<br>"start""end""center" | "center" |
| alignOffset | An offset in pixels from the "start" or "end" alignment options.<br>number | 0 |
| translucent | Whether the popover surface should be translucent.<br>boolean | false |
| className | Additional class name to apply to the popover content, you usually don't want to set this, but ag-grid needs it to render a custom editor properly<br>string | - |
| autoFocus | Auto focus the popover content when it is opened.<br>boolean | true |

```
<Popover>
  <Popover.Trigger>
    ...
  </Popover.Trigger>
  <Popover.Content minWidth="auto" side="top">
    ...
  </Popover.Content>
</Popover>
```
```
<Popover showOnHover>
  <Popover.Trigger>
    ...
  </Popover.Trigger>
  <Popover.Content>
    ...
  </Popover.Content>
</Popover>
```
```
const Example = () => {
  return (
    <Popover>
      <Popover.Trigger>
        <Button color="primary">Generate</Button>
      </Popover.Trigger>
      <Popover.Content side="right" surface="glass">
        <ControllerForm />
      </Popover.Content>
    </Popover>
  )
}

const ControllerForm = () => {
  const [value, setValue] = useState("")
  const [submitting, setSubmitting] = useState(false)
  const { shake, close } = usePopoverController()

  const handleSubmit = (evt: FormEvent) => {
    evt.preventDefault()

    if (!value) {
      shake()
      return
    }

    setSubmitting(true)
    setTimeout(close, 2000)
  }
  return (
    <form onSubmit={handleSubmit}>
      <Textarea value={value} onChange={setValue} />
      <ActionBar loading={submitting} />
    </form>
  )
}
```
