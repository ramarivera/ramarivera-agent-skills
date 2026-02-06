# TagInput

## Enter multiple unique tags

### Usage

```
import { TagInput } from "@openai/apps-sdk-ui/components/TagInput";

```

### Reference

example@openai.com

```
<div
  style={{
    width: 350
  }}
>
  <TagInput
    autoFocus
    placeholder="example@openai.com"
    rows={3}
    validator={function Xs(){}}
  />
</div>
```

| Name | Description | Default | Control |
| --- | --- | --- | --- |
| placeholder | Placeholder text for the input<br>string | - |  |
| validator | A function that returns whether a given value is a valid tag.<br>Invalid tags are highlighted in red.<br>Tags are evaluated for validity only on creation; changing the validator function later has no effect<br>((value: string) => boolean) | - | - |
| rows | The minimum number of rows for the tag input<br>number | 1 |  |
| autoFocus | Whether to focus this input on mount<br>boolean | false | FalseTrue |
| defaultValue | The state of the tag input when it is initially rendered, used when uncontrolled<br>Tag\[\] | - | Set object |
| value | The value of the tag input, used to control the tag input<br>Tag\[\] | - | Set object |
| id | Allows the tag input to be targeted with htmlFor<br>string | - | Set string |
| size | Corresponds with Input height when rows=1<br>"md""lg""xl""2xl""3xl" | "xl" | mdlgxl2xl3xl |
| onChange | Callback function invoked when the tag list changes<br>((tags: Tag\[\]) => void) | - | - |
| maxTags | The maximum number of tags allowed before the input is disabled; displays a counter below the input<br>number | - | Set number |
| delimiters | Controls what characters will count towards creating a new tag<br>string\[\] | \[',', ' '\] | Set object |
| disabled | Disables the tag input visually and from interactions<br>boolean | - | Set boolean |
