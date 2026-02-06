# RadioGroup

## Semantic radio option selection

Chocolate

Vanilla

Yes

## Usage

```
import { RadioGroup } from "@/components/ui/RadioGroup";

```

### Notification frequency

Daily

Weekly

Monthly

Never

```
() => {
  const [frequency, setFrequency] = useState("daily");
  return <div>
      <h3 className="font-semibold text-sm mb-3">Notification frequency</h3>
      <RadioGroup direction="col" value={frequency} onChange={setFrequency} aria-label="Notification frequency">
        <RadioGroup.Item value="daily">Daily</RadioGroup.Item>
        <RadioGroup.Item value="weekly">Weekly</RadioGroup.Item>
        <RadioGroup.Item value="monthly">Monthly</RadioGroup.Item>
        <RadioGroup.Item value="never">Never</RadioGroup.Item>
      </RadioGroup>
    </div>;
}
```

## Reference

### `RadioGroup`

| Name | Description | Default |
| --- | --- | --- |
| disabled | Controls whether the entire radio group is disabled<br>boolean | false |
| defaultValue | string | - |
| value | string | - |
| name | string | - |
| onChange | ((value: T) => void) | - |
| aria-label\* | Accessible label for the radio options<br>string | - |
| direction | Determines the layout direction of the radio items<br>"row""col" | "row" |
| className | Class applied to the radio group container<br>string | - |
| required | boolean | - |

### `RadioGroup.Item`

| Name | Description | Default |
| --- | --- | --- |
| value\* | string | - |
| disabled | Determines if a given radio item is disabled<br>boolean | false |
| required | boolean | - |
| block | boolean | false |
| className | string | - |

```
<RadioGroup
  aria-label="Sample options"
  direction="col"
>
  <RadioGroup.Item value="option1">
    Option 1
  </RadioGroup.Item>
  <RadioGroup.Item value="option2">
    Option 2
  </RadioGroup.Item>
  <RadioGroup.Item value="option3">
    Option 3
  </RadioGroup.Item>
</RadioGroup>
```
```
<RadioGroup disabled>
  ...
</RadioGroup>
```
```
<RadioGroup>
  <RadioGroup.Item disabled>
  ...
</RadioGroup>
```
```
() => <RadioGroup className="flex-col w-[390px] gap-4" onChange={() => {}} aria-label="Sample options">
    <RadioGroup.Item className="gap-2.5" value="basic">
      <div>
        <h4 className="font-semibold mb-1">Basic Plan</h4>
        <p className="text-secondary text-sm">5 GB storage • Email support • Free</p>
      </div>
    </RadioGroup.Item>
    <hr className="border-default" />
    <RadioGroup.Item className="gap-2.5" value="standard">
      <div>
        <h4 className="font-semibold mb-1">Standard Plan</h4>
        <p className="text-secondary text-sm">100 GB storage • Priority email support • $9.99/m</p>
      </div>
    </RadioGroup.Item>
    <hr className="border-default" />
    <Tooltip maxWidth={258} content={<>
          Contact our <TextLink href="#">support team</TextLink> for more information on enterprise
          plans.
        </>} interactive>
      <Tooltip.Trigger>
        <RadioGroup.Item className="gap-2.5" value="enterprise" disabled>
          <div>
            <h4 className="font-semibold mb-1">Enterprise Plan</h4>
            <p className="text-secondary text-sm">
              Unlimited storage • 24/7 phone support • Custom pricing
            </p>
          </div>
        </RadioGroup.Item>
      </Tooltip.Trigger>
    </Tooltip>
  </RadioGroup>
```
