## Allow users to easily copy to clipboard

### Usage

```
import { CopyTooltip } from "@openai/apps-sdk-ui/components/Tooltip";

```

### Reference

sess\_12345abcdefg

```
<CopyTooltip copyValue="Very cool content to copy">
  <Tooltip.TriggerDecorator>
    sess_12345abcdefg
  </Tooltip.TriggerDecorator>
</CopyTooltip>
```

| Name | Description | Default | Control |
| --- | --- | --- | --- |
| copyValue\* | Value to copy to the clipboard<br>string | - | - |
| openDelay | Delay of when the tooltip is shown from first interaction, in milliseconds.<br>number | 150 | 0\-\- / 1500 |
| align | The preferred alignment against the trigger. May change when collisions occur.<br>"start""end""center" | "center" | startendcenter |
| alignOffset | An offset in pixels from the "start" or "end" alignment options.<br>number | 0 | 0\-\- / 40 |
| side | The preferred side of the trigger to render against when open. Will be reversed when collisions occur.<br>"top""right""bottom""left" | "top" | toprightbottomleft |
| sideOffset | The distance in pixels from the trigger.<br>number | 5 | 0\-\- / 40 |
