# Alert

## Call attention to a specific message or warning

## Usage

```
import { Alert } from "@openai/apps-sdk-ui/components/Alert";

```

```
<Alert
  actions={<Button color="primary" pill variant="soft">Dismiss</Button>}
  description="We'll be offline 2 - 4 AM UTC on July 14 while we upgrade our database."
  title="Scheduled maintenance"
/>
```

## Reference

| Name | Description | Default |
| --- | --- | --- |
| title | Title displayed in the alert.<br>ReactNode | - |
| description | Description text displayed in the alert<br>ReactNode | - |
| actions | Actions associated with the Alert.<br>ReactNode | - |
| color | Color for the button<br>"primary""success""info""discovery""danger""warning""caution" | "primary" |
| variant | Style variant for the Button<br>"soft""solid""outline" | "outline" |
| actionsPlacement | Sets the placement of `actions` always on the end or the bottom. Default behavior is automatic placement based on sizing.<br>"end""bottom" | - |
| indicator | Optional override for the default indicator of the alert. When `false`, no indicator is shown.<br>ReactNode | - |
| className | Class applied to the alert container<br>string | - |
| actionsClassName | Class applied to the actions container<br>string | - |
| ref | Ref applied to the alert container<br>Ref<HTMLDivElement> | - |

```
<Alert title="Your current access level limits what you can view or modify" />
```
```
<Alert description={<>We're working on centralizing SCIM and invite settings. For now, setup is handled within individual product settings.{' '}<TextLink href="#">Learn more</TextLink></>} />
```
```
<Alert
  variant="soft"
  color="warning"
  title="Password expires in 3 days"
  description="Update it now to avoid losing access to your account."
  actions={<Button color="primary" pill>Update password</Button>}
/>
```
```
<Alert
  title="Our terms of service has been updated"
  description="We've updated our terms to clarify how we handle data, billing, and user permissions. Please review and accept the latest terms to avoid impacting your service."
  actions={(
    <>
      <Button color="primary" pill variant="soft">Set reminder</Button>
      <Button color="primary" pill variant="solid">Review terms</Button>
    </>
  )}
  actionsPlacement="bottom"
/>
```
```
<Alert
  indicator={<Lightbulb />}
  description={(
    <>
      We're working on centralizing SCIM and invite settings. For now, setup is handled within
      individual product settings. <TextLink href="#">Learn more</TextLink>
    </>
  )}
/>
```
```
<Alert
  indicator={false}
  description="Version 2.18.5 rolls out behind-the-scenes tweaks to caching and background sync. You don’t need to do anything—updates apply automatically the next time you open the app. Most changes are performance-related; if you notice smoother scrolling or slightly faster load times, that's why."
/>
```
```
<Alert
  className="items-start"
  title="Try our new dashboard layout"
  description="We've introduced a streamlined layout that makes using the dashboard even easier. You can switch back any time."
  actions={(
    <>
      <Button color="primary" variant="soft" pill>
        Dismiss
      </Button>
      <Button color="primary" variant="solid" pill>
        Try it
      </Button>
    </>
  )},
/>
```
