# DateRangePicker

## Select a date range with an interactive calendar

## Usage

```
import { DateRangePicker } from "@openai/apps-sdk-ui/components/DateRangePicker";

```

```
<DateRangePicker
  value={selectedDateRange}
  onChange={(nextDateRange) => {
    setSelectedDateRange(nextDateRange);
  }}
  shortcuts={dayShortcuts}
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
| value\* | The selected date range value.<br>DateRangenull | - |
| onChange\* | Handler that is triggered when the date range changes.<br>(nextValue: DateRange \| null, shortcut?: DateRangeShortcut \| undefined) => void | - |
| min | Defines the earliest selectable date (inclusive).<br>DateTime<boolean> | - |
| max | Defines the latest selectable date (inclusive).<br>DateTime<boolean> | - |
| maxRangeDays | Maximum length of the selectable range in days (inclusive).<br>When set, the end date cannot be more than this many days after the start date.<br>number | - |
| shortcuts | List of date range shortcuts displayed for quick selection, shown to the left of the calendar.<br>DateRangeShortcut\[\] | - |
| side | The preferred side of the trigger to render against when open. Will be reversed when collisions occur.<br>"top""right""bottom""left" | "bottom" |
| sideOffset | The distance in pixels from the trigger.<br>number | 8 |
| align | The preferred alignment against the trigger. May change when collisions occur.<br>"start""end""center" | "center" |
| alignOffset | An offset in pixels from the "start" or "end" alignment options.<br>number | 0 |
| disabled | Disables the select visually and from interactions<br>boolean | false |
| placeholder | Placeholder text for the select<br>string | "Select date range..." |
| variant | Style variant for the select trigger<br>"soft""outline""ghost" | "outline" |
| dropdownIconType | Icon displayed in the far right of the select trigger<br>"none""chevronDown""dropdown" | "dropdown" |
| triggerClassName | Custom class applied to the select trigger<br>string | - |
| triggerShowIcon | Display calendar icon at the start of the trigger<br>boolean | true |
| triggerStepperUnit | Allows the trigger to display as a stepper when the selected date matches the unit.<br>Currently 'month' is the only supported unit.<br>"month" | - |
| triggerDateFormat | Format of dates displayed in the trigger<br>string | "\\"MM/dd/yy\\"" |
| block | Extends select to 100% of available width.<br>boolean | true |

```
const today = DateTime.local()
const minDate = today.minus({ days: 120 }).startOf("day")
const maxDate = today.endOf("day")
const [selectedDateRange, setSelectedDateRange] = useState<DateRange | null>(() =>
  getMonthStartAndEnd(today, { min: minDate, max: maxDate }),
)

return (
  <DateRangePicker
    ...
    min={minDate}
    max={maxDate}
  />
)
```
```
<DateRangePicker
  ...
  shortcuts={dayShortcuts}
/>
```
```
<DateRangePicker
  ...
  triggerStepperUnit: "month",
/>
```
