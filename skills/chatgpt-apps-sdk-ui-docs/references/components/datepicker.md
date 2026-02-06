# DatePicker

## Select a single date with an interactive calendar

## Usage

```
import { DatePicker } from "@openai/apps-sdk-ui/components/DatePicker";

```

```
<DatePicker
  value={selectedDate}
  onChange={(nextDate) => {
    setSelectedDate(nextDate);
  }}
  clearable
  pill
/>
```

## Reference

| Name | Description | Default |
| --- | --- | --- |
| size | Determines size of the size and spacing of the control.

| 3xs | 2xs | xs | sm | md | lg | xl | 2xl | 3xl |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| `22px` | `24px` | `26px` | `28px` | `32px` | `36px` | `40px` | `44px` | `48px` |

| pill | Determines if the select trigger should be a fully rounded pill shape<br>boolean | false |
| clearable | Display a clear action that allows the select to be unset.<br>boolean | false |
| id\* | Allow targeting the input for forms and accessibility.<br>string | - |
| value\* | The selected date value.<br>DateTime<boolean> \| null | - |
| onChange\* | Handler that is triggered when the date changes.<br>(nextValue: DateTime<boolean> \| null) => void | - |
| min | Defines the earliest selectable date (inclusive).<br>DateTime<boolean> | - |
| max | Defines the latest selectable date (inclusive).<br>DateTime<boolean> | - |
| side | The preferred side of the trigger to render against when open. Will be reversed when collisions occur.<br>"top""right""bottom""left" | "bottom" |
| sideOffset | The distance in pixels from the trigger.<br>number | 8 |
| align | The preferred alignment against the trigger. May change when collisions occur.<br>"start""end""center" | "center" |
| alignOffset | An offset in pixels from the "start" or "end" alignment options.<br>number | 0 |
| disabled | Disables the select visually and from interactions<br>boolean | false |
| placeholder | Placeholder text for the select<br>string | "Select date..." |
| variant | Style variant for the select trigger<br>"soft""outline""ghost" | "outline" |
| dropdownIconType | Icon displayed in the far right of the select trigger<br>"none""chevronDown""dropdown" | "dropdown" |
| triggerClassName | Custom class applied to the select trigger<br>string | - |
| triggerShowIcon | Display calendar icon at the start of the trigger<br>boolean | true |
| triggerDateFormat\* | Format of dates displayed in the trigger<br>string | - |
| block | Extends select to 100% of available width.<br>boolean | true |

```
const today = DateTime.local()
const minDate = today.minus({ days: 30 }).startOf("day")
const maxDate = today.plus({ days: 30 }).endOf("day")
const [selectedDate, setSelectedDate] = useState<DateTime | null>(today)

return (
  <DatePicker
    ...
    min={minDate}
    max={maxDate}
  />
)
```
```
<DatePicker
  ...
  triggerShowIcon={false}
  placeholder="Choose a date"
/>
```
```
<DatePicker
  ...
  disabled
/>
```
