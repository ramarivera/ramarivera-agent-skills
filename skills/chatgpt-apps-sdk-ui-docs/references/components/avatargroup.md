# AvatarGroup

## Display avatars as a single stack

+5WT

## Usage

```
import { AvatarGroup } from "@openai/apps-sdk-ui/components/Avatar";

```

```
<AvatarGroup size={42}>
  <Avatar name="Tyler" imageUrl="https://gravatar.com/avatar/xyz" />
  <Avatar name="Jane" color="primary" variant="solid" />
  <Avatar name="Tech support" Icon={Robot} variant="solid" />
  <Avatar overflowCount={5} />
</AvatarGroup>
```

## Reference

| Name | Description | Default |
| --- | --- | --- |
| stack | Determines stacking layer order<br>"start""end" | "start" |
| size | Size all avatars in the group, in pixels.<br>number | - |
| className | Class name passed to the group container<br>string | - |

```
<AvatarGroup
  size={48}
  stack="start"
>
  <Avatar
    color="info"
    name="Tyler"
  />
  <Avatar
    color="discovery"
    name="Jane"
  />
  <Avatar
    color="danger"
    name="Will"
  />
  <Avatar overflowCount={5} />
</AvatarGroup>
```
