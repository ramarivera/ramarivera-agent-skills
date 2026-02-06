# Slider

## Fine-tune values within a set range

### Usage

```
import { Slider } from "@openai/apps-sdk-ui/components/Slider";

```

### Reference

Example field

ms

```
<div
  style={{
    width: 300
  }}
>
  <Slider
    label="Example field"
    max={2000}
    min={0}
    onChange={function Xs(){}}
    resetValue={1000}
    step={10}
    unit="ms"
    value={1000}
  />
</div>
```

| Name | Description | Default | Control |
| --- | --- | --- | --- |
| label | Optional label for the slider, which can be a string or React node.<br>ReactNode | - |  |
| min\* | The minimum value the slider can have<br>number | - |  |
| max\* | The maximum value the slider can have<br>number | - |  |
| resetValue | Value that will be offered as a "reset to default" option<br>number | - |  |
| step\* | The step increment between slider values<br>number | - |  |
| unit | Unit to display next to the slider value (e.g., ms, px)<br>string | - |  |
| disabled | boolean | - | FalseTrue |
| value\* | The current value of the slider<br>number | - | - |
| resetTooltip | String that will be displayed in the tooltip<br>string | "Reset to default" | Set string |
| prefixUnit | Unit to display to the right of the slider value (e.g., $)<br>string | - | Set string |
| marks | List of marks to display below the slider track<br>SliderMark\[\] | - | - |
| trackColor | Color of the slider track<br>string | - |  |
| rangeColor | Color of the slider progress along the track<br>string | - |  |
| className | string | - | - |
| onChange\* | Callback function invoked when the slider value changes.

(value: number) => void

|     |     |
| --- | --- |
| `value` | The new value of the slider. | | - | - |
| onBlur | FocusEventHandler<HTMLInputElement> | - | - |
| onFocus | FocusEventHandler<HTMLInputElement> | - | - |

```
<Slider
    label={(
        <Tooltip content="More details about this field">
            <TriggerDecorator>Example field</TriggerDecorator>
        </Tooltip>
    )}
    max={2000}
    min={0}
    onChange={() => {}}
    resetValue={1000}
    step={10}
    unit="ms"
    value={1000}
  />
```
```
<Slider
    value={value}
    onChange={() => {}}
    label="Passing grade"
    min={1}
    max={3}
    step={1}
    marks={[\
        { value: 1, label: "Inaccurate" },\
        { value: 2, label: "Some inaccuracies" },\
        { value: 3, label: "Accurate" },\
    ]}
    trackColor="#61C454"
    rangeColor="#EF4146"
/>
```
