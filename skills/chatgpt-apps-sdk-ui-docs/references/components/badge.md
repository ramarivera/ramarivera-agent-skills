# Badge

## Emphasize details with a status indicator

Successful

In progress

Failed

Beta

## Usage

```
import { Badge } from "@openai/apps-sdk-ui/components/Badge";

```

```
<Badge
  color="success"
  size="md"
>
  New
</Badge>
```

## Reference

| Name | Description | Default |
| --- | --- | --- |
| children\* | Content rendered inside the badge<br>ReactNode | - |
| color | Color of the badge, related to its meaning or intent<br>"secondary""success""info""discovery""danger""warning" | "secondary" |
| size | Size scale of the badge

| sm | md | lg |
| --- | --- | --- |
| `18px` | `22px` | `24px` |

| pill | Determines if the badge should be a fully rounded pill shape<br>boolean | false |
| className | Class applied to the badge<br>string | - |
| variant | Visual style of the badge<br>"soft""solid""outline" | "soft" |

```
<Badge color="warning" size="lg">
  <Beta /> Beta
</Badge>
```
```
<Badge
  className="gap-1.5"
  color="secondary"
  size="lg"
>
  <LoadingIndicator />
  In progress
</Badge>
```
