# SegmentedControl

## Toggle through grouped options

## Usage

```
import { SegmentedControl } from "@openai/apps-sdk-ui/components/SegmentedControl";

```

```
<SegmentedControl
  aria-label="Select view"
  onChange={function Xs(){}}
  value="all"
>
  <SegmentedControl.Option value="all">
    All
  </SegmentedControl.Option>
  <SegmentedControl.Option value="failed">
    Failed
  </SegmentedControl.Option>
  <SegmentedControl.Option value="successful">
    Successful
  </SegmentedControl.Option>
</SegmentedControl>
```

## Reference

### `SegmentedControl`

| Name | Description | Default |
| --- | --- | --- |
| value\* | Controlled value for the group<br>string | - |
| onChange | Callback for when a new value is selected<br>((nextValue: T) => void) | - |
| onClick | Callback any time the control is clicked (even if a new value was not selected)<br>(() =\> void) | - |
| aria-label\* | Text read aloud to screen readers when the control is focused<br>string | - |
| size | Controls the size of the segmented control

| 3xs | 2xs | xs | sm | md | lg | xl | 2xl | 3xl |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| `22px` | `24px` | `26px` | `28px` | `32px` | `36px` | `40px` | `44px` | `48px` |

| gutterSize | Controls gutter on the edges of the button, defaults to value from `size`.

| 2xs | xs | sm | md | lg | xl |
| --- | --- | --- | --- | --- | --- |
| `6px` | `8px` | `10px` | `12px` | `14px` | `16px` |

| disabled | Disable the entire group<br>boolean | - |
| block | Display the control as a block element with equal width segments<br>boolean | false |
| pill | Determines if the segment control, and its options, should be a fully rounded pill shape.<br>boolean | true |
| className | string | - |

### `SegmentedControl.Option`

| Name | Description | Default |
| --- | --- | --- |
| value\* | Option value<br>string | - |
| aria-label | Text read aloud to screen readers when the option is focused<br>string | - |
| children\* | Content to render in the option<br>ReactNode | - |
| disabled | Disable the individual option<br>boolean | - |

```
<SegmentedControl block>
  <SegmentedControl.Option />
  <SegmentedControl.Option />
  <SegmentedControl.Option />
</SegmentedControl>
```
```
<SegmentedControl disabled>
  <SegmentedControl.Option />
  <SegmentedControl.Option />
  <SegmentedControl.Option />
</SegmentedControl>
```
```
<SegmentedControl>
  <SegmentedControl.Option />
  <SegmentedControl.Option />
  <SegmentedControl.Option disabled />
</SegmentedControl>
```
```
<div className="flex">
  <SegmentedControl>
    {...}
  </SegmentedControl>
</div>
```
