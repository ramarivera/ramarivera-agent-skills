# Checkbox

## Toggle control for on and off states

## Usage

```
import { Checkbox } from "@openai/apps-sdk-ui/components/Checkbox";

```

```
<Checkbox
  label="Same as billing address"
/>
```

## Reference

| Name | Description | Default |
| --- | --- | --- |
| disabled | When `true`, prevents the user from interacting with the checkbox.<br>boolean | - |
| defaultChecked | The state of the checkbox when it is initially rendered. Use when you do not need to control its state.<br>boolean"indeterminate" | - |
| label | Optional accessible label rendered to the right of the checkbox.<br>ReactNode | - |
| id | The `id` of the checkbox.<br>string | - |
| checked | The controlled state of the checkbox. Must be used in conjunction with `onCheckedChange`.<br>boolean"indeterminate" | - |
| onCheckedChange | Event handler called when the state of the checkbox changes.<br>((nextState: boolean) => void) | - |
| onBlur | Event handler called when the checkbox looses focus.<br>FocusEventHandler<HTMLButtonElement> | - |
| onFocus | Event handler called when the checkbox gains focus.<br>FocusEventHandler<HTMLButtonElement> | - |
| required | When `true`, indicates that the user must check the checkbox before the owning form can be submitted.<br>boolean | - |
| name | The name of the checkbox. Submitted with its owning form as part of a name/value pair.<br>string | - |
| value | The value given as data when submitted with a `name`.<br>string | - |
| className | CSS classes applied to wrapper node<br>string | - |
| orientation | The orientation of the checkbox relative to the label.<br>"right""left" | "left" |

```
<Checkbox
  checked="indeterminate"
/>
```
