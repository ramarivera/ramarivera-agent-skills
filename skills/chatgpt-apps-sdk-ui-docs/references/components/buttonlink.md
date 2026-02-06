# ButtonLink

## `<Button>` as a semantic anchor element

## Usage

```
import { ButtonLink } from "@openai/apps-sdk-ui/components/Button";

```

```
<ButtonLink
  color="primary"
  href="https://platform.openai.com"
>
  View API Keys
  <ArrowRight />
</ButtonLink>
```

## Reference

| Name | Description | Default |
| --- | --- | --- |
| children | Content rendered inside of the Button<br>ReactNode | - |
| color | Color for the button<br>string | "secondary" |
| size | Controls size of the button, specifically height, but also includes defaults for `gutterSize`, `iconSize`, `font-size`, etc.

| 3xs | 2xs | xs | sm | md | lg | xl | 2xl | 3xl |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| `22px` | `24px` | `26px` | `28px` | `32px` | `36px` | `40px` | `44px` | `48px` |

| href | string | - |
| block | Determines if the button should take up 100% of available width<br>boolean | false |
| disabled | Disables the button visually and from interactions<br>boolean | false |
| pill | Determines if the button should be a fully rounded pill shape<br>boolean | true |
| className | Custom class applied to the Button element<br>string | - |
| variant | Style variant for the Button<br>"soft""solid""outline""ghost" | "\\"solid\\"" |
| disabledTone | Controls the visual tone when the button is disabled. "relaxed" will use a default cursor instead of not-allowed.<br>"relaxed" | - |
| opticallyAlign | Applies a negative margin using the current gutter to optically align the button<br>with surrounding content.<br>"start""end" | - |
| iconSize | Controls the size of icons within the button, defaults to value from `size`.

| xs | sm | md | lg | xl | 2xl |
| --- | --- | --- | --- | --- | --- |
| `14px` | `16px` | `18px` | `20px` | `22px` | `24px` |

| gutterSize | Controls gutter on the edges of the button, defaults to value from `size`.

| 3xs | 2xs | xs | sm | md | lg | xl |
| --- | --- | --- | --- | --- | --- | --- |
| `4px` | `6px` | `8px` | `10px` | `12px` | `14px` | `16px` |

| external | Explicity specify that the link is an external link. This should be<br>automatically detected based on the URL, but in some cases (e.g.<br>my-app://foo) you may want to explicitly set this.<br>boolean | - |
| as | Override the default component used for the link. This is useful for<br>using a routing library, or SSR rendering.<br>purposes.<br>"a" \| ComponentType<any> | 'a' |

```
() => <ButtonLink href="/some-path" color="primary">
    Internal link <ArrowRight />
  </ButtonLink>
```
```
() => <ButtonLink href="https://openai.com" color="primary">
    External link <ArrowUpRight />
  </ButtonLink>
```
```
<ButtonLink
  color="info"
  href="https://platform.openai.com"
  size="lg"
  variant="soft"
>
  <Globe />
  {' '}View website
</ButtonLink>
```
```
<div className="w-[290px] text-center p-2 border border-dashed border-alpha/20 rounded-md">
  <ButtonLink
    as="a"
    block
    color="primary"
    href="https://platform.openai.com"
    size="lg"
  >
    Continue to dashboard
  </ButtonLink>
</div>
```
```
<ButtonLink
  href="https://platform.openai.com"
  color="primary"
  disabled
  onClick={alertMsg}
>
  <Key />
  View API Keys
</ButtonLink>
```
## Configure your Router

### Provider

```
// In the root of your App
import {AppsSDKUIProvider} from "@openai/apps-sdk-ui/components/AppsSDKUIProvider"
import {Link} from "react-router"

// Set up types
declare global {
  interface AppsSDKUIConfig {
    LinkComponent: typeof Link
  }
}

// Wrap your app in AppsSDKUIProvider and pass in your router's Link component.
export function App() {
  return (
    <AppsSDKUIProvider linkComponent={Link}>
      {/* other providers... */}
    </AppsSDKUIProvider>
  )
}

// elsewhere - everything just works!
<ButtonLink to={{ pathname: "/help" }} prefetch="intent">
  Get Help
</ButtonLink>

```

### Component-level

You can also pass your Link component to the `as` prop.

```
import {Link} from "next/link"

<ButtonLink as={Link} href="/dashboard">
  View Dashboard
</ButtonLink>

```
