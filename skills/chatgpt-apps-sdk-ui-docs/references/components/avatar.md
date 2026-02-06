# Avatar

## Display user identities with either text, photo, or an icon

TW

## Usage

```
import { Avatar } from "@openai/apps-sdk-ui/components/Avatar";

```

```
<Avatar
  name="Jane"
  size={48}
/>
```

## Reference

| Name | Description | Default |
| --- | --- | --- |
| name | Name used to display initials from<br>string | "" |
| size | Size of the avatar's width & height, in pixels.<br>number | - |
| className | Class name applied to the avatar<br>string | - |
| overflowCount | Display a formatted count of overflow objects.<br>number | - |
| color | Color used for the avatar<br>"primary""secondary""success""info""discovery""danger" | "secondary" |
| variant | Style variant of the avatar<br>"soft""solid" | "soft" |
| imageUrl | URL of the image to display as the avatar<br>string | - |
| Icon | Icon to render in the avatar circle<br>ComponentType<SVGProps<SVGSVGElement>> | - |
| onClick | Optional click handler, which also enables semantic interactions<br>(() =\> void) | - |
| onPointerDown | Optional pointer handler, which also enables semantic interactions<br>(() =\> void) | - |

```
<Avatar
  name="David"
  size={48}
/>
```
```
<Avatar
  imageUrl="https://gravatar.com/avatar/9531b260b9693f3394bea8646c6ea141ce58fe5a138b7db7729d60a4c5dde552"
  name="Tyler"
  size={48}
/>
```
```
<Avatar
  Icon={Robot}
  size={48}
/>
```
```
<Avatar
  overflowCount={9}
  size={48}
/>
```
```
<Avatar
  name="David"
  size={48}
/>
```
```
<Avatar
  className="rounded-lg"
  color="primary"
  name="Acme, co."
  size={48}
  variant="solid"
/>
```
```
<Avatar
  name="Will"
  size={48}
  onClick={saySup}
/>
```
