# TextLink

## Semantic link used for both internal and external links

Read moreExternal link

## Usage

```
import { TextLink } from "@openai/apps-sdk-ui/components/TextLink"

```

```
<p>
  You can use the{' '}
  <TextLink href="#">responses endpoint</TextLink>{' '}
  to generate text. You can either use the API directly from an HTTP client of your choice, or use one of OpenAI's{' '}
  <TextLink href="#">official SDKs</TextLink>{' '}
  for your preferred language.
</p>
```

## Reference

| Name | Description | Default |
| --- | --- | --- |
| href | string | - |
| primary | Applies a primary color to the link and removes the default `underline`.<br>boolean | false |
| underline | Apply `text-decoration: underline` to the Link<br>boolean | true |
| forceExternal | Force external link behavior, which is automatically detected based on the URL.<br>boolean | - |
| as | Override the default component used for the link. This is useful for<br>using a routing library, or SSR rendering.<br>purposes.<br>"a" \| ComponentType<any> | 'a' |

```
<p className="text-secondary">
  You can use the{' '}
  <TextLink href="#">
    responses endpoint
  </TextLink>
  {' '}to generate text. You can either use the API directly from an HTTP client of your choice, or use one of OpenAI's{' '}
  <TextLink href="#">
    official SDKs
  </TextLink>
  {' '}for your preferred language.
</p>
```
```
<p>
  Sample text with a{' '}
  <TextLink
    href="#"
    primary
  >
    primary link
  </TextLink>
</p>
```
```
<p className="text-secondary">
  Sample text with a{' '}
  <TextLink
    href="#"
  >
    subtle link
  </TextLink>
</p>
```
```
<TextLink primary underline href="https://openai.com">
  External link <ArrowUpRight />
</TextLink>
```
```
<TextLink className="font-semibold" underline={false} href="#">
  Contact support <ArrowRight />
</TextLink>
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
<TextLink to={{ pathname: "/help" }} prefetch="intent">
  Get Help
</TextLink>

```

### Component-level

You can also pass your Link component to the `as` prop.

```
import {Link} from "next/link"

<TextLink as={Link} href="/dashboard">
  View Dashboard
</TextLink>

```
