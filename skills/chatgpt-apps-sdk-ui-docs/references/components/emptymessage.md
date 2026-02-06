# EmptyMessage

## Gracefully inform users when there's nothing to see

### Usage

```
import { EmptyMessage } from "@openai/apps-sdk-ui/components/EmptyMessage"

```

### Reference

Your evaluations will appear here

Create an evaluation to assess your model's responses

Create

```
() => <EmptyMessage>
    <EmptyMessage.Icon>
      <Explore />
    </EmptyMessage.Icon>
    <EmptyMessage.Title>Your evaluations will appear here</EmptyMessage.Title>
    <EmptyMessage.Description>
      Create an evaluation to assess your model's responses
    </EmptyMessage.Description>
    <EmptyMessage.ActionRow>
      <Button color="primary" onClick={() => {}} size="lg">
        <Plus className="mr-[-2px]" />
        Create
      </Button>
    </EmptyMessage.ActionRow>
  </EmptyMessage>
```

#### `EmptyMessage`

| Name | Description | Default |
| --- | --- | --- |
| className | string | - |
| fill | Determines how the container fills available space<br>"none""static""absolute" | "static" |

#### `EmptyMessage.Icon`

| Name | Description | Default |
| --- | --- | --- |
| size | "sm""md" | "md" |
| color | "secondary""danger""warning" | "secondary" |
| className | string | - |

```
() => <EmptyMessage>
    <EmptyMessage.Icon color="danger">
      <Mic />
    </EmptyMessage.Icon>
    <EmptyMessage.Title color="danger">
      Enable microphone access in your browser's settings.
    </EmptyMessage.Title>
  </EmptyMessage>
```
```
() => <EmptyMessage fill="none">
    <EmptyMessage.Icon size="sm">
      <Search />
    </EmptyMessage.Icon>
    <EmptyMessage.Description>
      No icons found matching <span className="font-semibold">"pizza"</span>
    </EmptyMessage.Description>
  </EmptyMessage>
```
