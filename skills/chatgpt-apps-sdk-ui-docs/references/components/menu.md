# Menu

## Structured actions in a dropdown list

## Usage

```
import { Menu } from "@openai/apps-sdk-ui/components/Menu"

```

```
() => <Menu>
    <Menu.Trigger>
      <Button color="primary" size="lg" variant="ghost">
        Sample menu <ChevronDown />
      </Button>
    </Menu.Trigger>
    <Menu.Content width={210} minWidth={210}>
      <Menu.Item>
        <p className="font-semibold">Sam Smith</p>
        <p className="text-secondary">sam.smith@gmail.com</p>
      </Menu.Item>
      <Menu.Separator />
      <Menu.Link href="/settings">Your profile</Menu.Link>
      <Menu.Link href="https://openai.com/policies/">Terms & policies</Menu.Link>
      <Menu.Item disabled onSelect={() => {}}>
        Feature flags
      </Menu.Item>
      <Menu.Separator />
      <Menu.Item onSelect={() => {}}>Logout</Menu.Item>
    </Menu.Content>
  </Menu>
```

## Reference

### `Menu`

| Name | Description | Default |
| --- | --- | --- |
| forceOpen | Force the menu to remain open or closed<br>boolean | - |
| onOpen | Callback triggered when the modal is opened<br>(() =\> void) | - |
| onClose | Callback triggered when the modal is closed<br>(() =\> void) | - |
| modal | When set to `true`, interaction with outside elements will be disabled and only menu content will be visible to screen readers.<br>boolean | false |

### `Menu.Trigger`

Renders the element that toggles the menu open and closed. You can use any interactive element (e.g., a button or icon) as the trigger. The trigger should be the user's point of interaction for revealing the menu options.

### `Menu.Content`

Renders the dynamic content for the menu. `Menu.Content` is mounted only while the menu is open.

| Name | Description | Default |
| --- | --- | --- |
| side | The preferred side of the trigger to render against when open. Will be reversed when collisions occur.<br>"top""right""bottom""left" | "bottom" |
| sideOffset | The distance in pixels from the trigger.<br>number | 4 |
| align | The preferred alignment against the trigger. May change when collisions occur.<br>"start""end""center" | "center" |
| alignOffset | An offset in pixels from the "start" or "end" alignment options.<br>number | -6 |
| width | Defines the `width` property of the content<br>number"auto" | auto |
| minWidth | Defines the `min-width` property of the content, in pixels.<br>number"auto" | auto |
| maxHeight | Defines the `max-width` property of the content, in pixels.<br>number | - |

### `Menu.Item`

Most common component for rendering menu list items. When `onSelect` is omitted, the item is rendered as non-interactive.

| Name | Description | Default |
| --- | --- | --- |
| className | string | - |
| onSelect | Callback triggered when the item is pressed<br>((event: Event) => void) | - |
| onClick | Callback triggered when the item is clicked<br>MouseEventHandler<HTMLDivElement> | - |
| disabled | Disables the menu item<br>boolean | - |

### `Menu.Link`

Renders a menu item as a navigational link. Use `Menu.Link` to create items that navigate to another page or route when selected. Accepts all props supported by the application's router link component, such as `to` or `href`, and ensures proper accessibility roles and keyboard behavior within the menu.

### `Menu.Separator`

Renders a divider between menu items

| Name | Description | Default |
| --- | --- | --- |
| className | string | - |

### `Menu.Sub`

Renders a wrapper for nested submenus within a menu. Use `Menu.Sub` to group a `Menu.SubTrigger` and a `Menu.SubContent`.

| Name | Description | Default |
| --- | --- | --- |
| forceOpen | Force the menu to remain open or closed<br>boolean | - |
| onOpen | Callback triggered when the modal is opened<br>(() =\> void) | - |
| onClose | Callback triggered when the modal is closed<br>(() =\> void) | - |

### `Menu.SubTrigger`

Renders a menu item that toggles its associated submenu. Must be used inside a `Menu.Sub`.

| Name | Description | Default |
| --- | --- | --- |
| className | string | - |
| disabled | boolean | - |

### `Menu.SubContent`

Renders the content panel for a submenu. Must follow a `Menu.SubTrigger` within a `Menu.Sub`.

| Name | Description | Default |
| --- | --- | --- |
| sideOffset | number | 4 |
| alignOffset | number | -6 |
| width | number"auto" | auto |
| minWidth | number"auto" | auto |
| maxHeight | number | - |

### `Menu.CheckboxItem`

Renders a menu item with a checkbox indicator.

| Name | Description | Default |
| --- | --- | --- |
| checked | Controlled checked state of the checkbox item<br>CheckedState | - |
| onCheckedChange | Event handler called when the checked state changes<br>((checked: boolean) => void) | - |
| className | Class applied to the checkbox item<br>string | - |
| onSelect | Callback triggered when the checkbox item is pressed<br>((event: Event) => void) | - |
| disabled | Disables the checkbox item<br>boolean | - |
| indicatorPosition | The orientation of the indicator within the checkbox item.<br>"start""end" | "end" |
| indicatorVariant | Visual treatment for the checkbox indicator.<br>"solid""ghost" | "solid" |

### `Menu.RadioGroup`

Renders a group of radio items in a menu.

| Name | Description | Default |
| --- | --- | --- |
| value\* | Controlled value<br>string | - |
| onChange\* | Fired when selection changes<br>(value: T) => void | - |
| indicatorPosition | The orientation of the indicator within the radio item.<br>"start""end" | "end" |

### `Menu.RadioItem`

Renders a menu item with a radio indicator – used inside `Menu.RadioGroup`.

| Name | Description | Default |
| --- | --- | --- |
| value\* | string | - |
| className | Class applied to the radio item<br>string | - |
| onSelect | Callback triggered when the radio item is pressed<br>((event: Event) => void) | - |
| disabled | Disables the radio item<br>boolean | - |

### `Menu.ItemActions`

Renders a container for additional actions that appear on the menu item. `Menu.ItemActions` automatically handles visibility of the actions based on hover, and will not trigger the item's `onSelect` behavior.

| Name | Description | Default |
| --- | --- | --- |
| className | string | - |

### `Menu.ItemAction`

Renders an action for use in the hover `Menu.ItemActions` container. Child is most likely to be a simple icon, which is passed to a `Button` component.

| Name | Description | Default |
| --- | --- | --- |
| onClick\* | (evt: MouseEvent<Element, MouseEvent>) => void | - |

```
<Menu.Content minWidth="auto">
  <Menu.Item onSelect={handleSelect}>
    <Functions height={16} width={16} /> Function
  </Menu.Item>
  ...
</Menu.Content>
```
```
() => <Menu>
    <Menu.Trigger>
      <Button color="primary" size="lg" variant="ghost">
        Options <ChevronDown />
      </Button>
    </Menu.Trigger>
    <Menu.Content minWidth={180}>
      <Menu.Item onSelect={() => {}}>Edit</Menu.Item>
      <Menu.Item onSelect={() => {}}>Duplicate</Menu.Item>
      <Menu.Separator />
      <Menu.Sub>
        <Menu.SubTrigger>More</Menu.SubTrigger>
        <Menu.SubContent>
          <Menu.Item onSelect={() => {}}>Move to project…</Menu.Item>
          <Menu.Item onSelect={() => {}}>Move to folder…</Menu.Item>
          <Menu.Separator />
          <Menu.Item onSelect={() => {}}>Advanced options…</Menu.Item>
        </Menu.SubContent>
      </Menu.Sub>
      <Menu.Separator />
      <Menu.Item onSelect={() => {}}>Share</Menu.Item>
      <Menu.Item onSelect={() => {}}>Add to favorites</Menu.Item>
      <Menu.Separator />
      <Menu.Item onSelect={() => {}}>Delete</Menu.Item>
    </Menu.Content>
  </Menu>
```
```
const [settings, setSettings] = useState({
  showGrid: true,
  showLabels: false,
  enableShadows: false,
})

return (
  <Menu>
    <Menu.Trigger>
      <Button variant="ghost" color="primary">
        Checkbox menu <ChevronDown />
      </Button>
    </Menu.Trigger>
    <Menu.Content minWidth={200}>
      <Menu.CheckboxItem
        checked={settings.showGrid}
        onCheckedChange={(checked) => setSettings((s) => ({ ...s, showGrid: checked }))}
        onSelect={(evt) => evt.preventDefault()}
        indicatorPosition="end"
        indicatorVariant="filled"
      >
        Show grid lines
      </Menu.CheckboxItem>
      <Menu.CheckboxItem
        checked={settings.showLabels}
        onCheckedChange={(checked) => setSettings((s) => ({ ...s, showLabels: checked }))}
        onSelect={(evt) => evt.preventDefault()}
        indicatorPosition="end"
        indicatorVariant="filled"
      >
        Display labels
      </Menu.CheckboxItem>
      <Menu.CheckboxItem
        checked={settings.enableShadows}
        onCheckedChange={(checked) => setSettings((s) => ({ ...s, enableShadows: checked }))}
        onSelect={(evt) => evt.preventDefault()}
        indicatorPosition="end"
        indicatorVariant="filled"
      >
        Enable shadows
      </Menu.CheckboxItem>
    </Menu.Content>
  </Menu>
)
```
```
<Menu>
  <Menu.Trigger>
    <Button color="primary" variant="ghost">
      Radio menu <ChevronDown />
    </Button>
  </Menu.Trigger>
  <Menu.Content align="start" minWidth="auto" width="auto">
    <Menu.RadioGroup
      indicatorPosition="end"
      value={value}
      onChange={setValue}
    >
      <Menu.RadioItem value="any">Any time</Menu.RadioItem>
      <Menu.RadioItem value="today">Today</Menu.RadioItem>
      <Menu.RadioItem value="last7d">Last 7 days</Menu.RadioItem>
      <Menu.RadioItem value="last30d">Last 30 days</Menu.RadioItem>
      <Menu.RadioItem value="last3m">Last 3 months</Menu.RadioItem>
    </Menu.RadioGroup>
  </Menu.Content>
</Menu>
```
```
<Menu.Content>
  <Menu.Item onSelect={handleSelect}>
    <span className="flex-1 truncate">Sample thread title</span>
    <Menu.ItemActions>
      <Menu.ItemAction>
        <Edit />
      </Menu.ItemAction>
      <Menu.ItemAction>
        <Delete />
      </Menu.ItemAction>
    </Menu.ItemActions>
  </Menu.Item>
  ...
</Menu.Content>
```
