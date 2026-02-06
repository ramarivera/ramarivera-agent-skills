# Switch

## Toggle control for on and off states

## Usage

```
import { Switch } from "@openai/apps-sdk-ui/components/Switch";

<Switch />
```

## Reference

| Name | Description | Default |
| --- | --- | --- |
| id | The `id` of the switch.<br>string | - |
| defaultChecked | The state of the switch when it is initially rendered. Use when you do not need to control its state.<br>boolean | - |
| checked | The controlled state of the switch. Must be used in conjunction with `onCheckedChange`.<br>boolean | - |
| label | Optional accessible label rendered to the right of the checkbox.<br>ReactNode | - |
| onCheckedChange | Event handler called when the state of the switch changes.<br>((nextState: boolean) => void) | - |
| onBlur | Event handler called when the checkbox looses focus.<br>FocusEventHandler<HTMLButtonElement> | - |
| onFocus | Event handler called when the checkbox gains focus.<br>FocusEventHandler<HTMLButtonElement> | - |
| disabled | When `true`, prevents the user from interacting with the switch.<br>boolean | - |
| required | When `true`, indicates that the user must check the switch before the owning form can be submitted.<br>boolean | - |
| name | The name of the switch. Submitted with its owning form as part of a name/value pair.<br>string | - |
| value | The value given as data when submitted with a `name`.<br>string | - |
| className | CSS classes applied to wrapper node<br>string | - |
| labelPosition | The position of the label relative to the switch.<br>"start""end" | "end" |

```
<Switch label="Notifications" />
```
```
<Switch
  label="Right aligned"
  labelPosition="start"
/>
```
```
<Switch
  defaultChecked
  name="field-set-as-default"
/>
```
```
const [checked, setChecked] = useState(false)

<Switch checked={checked} onCheckedChange={setChecked} />
```
```
<div className="flex gap-6">
  <Switch disabled />
  <Switch
    checked
    disabled
  />
</div>
```
