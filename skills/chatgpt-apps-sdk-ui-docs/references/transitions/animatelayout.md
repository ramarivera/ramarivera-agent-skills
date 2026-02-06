# AnimateLayout

## Animate width & height of components as they mount and unmount

### Usage

```
import { AnimateLayout } from "@openai/apps-sdk-ui/components/Transition"

```

### Overview

`<AnimateLayout>` is an abstraction around `<TransitionGroup>` for batteries-included transition animations that can also animate `height` and `width` of transitions.

All of the same properties from `<Animate>` are supported here, as well as new properties for customizing the timing of layout transitions - `layoutEnter`, `layoutExit`, and `layoutMove`.

### When to use

`<AnimateLayout>` is great for transitions should naturally affect layout of surrounding DOM nodes.

These animations should be for transitioning between two states that occupy _the same space_, such as:

- _nothing_ → Component
- Component → _nothing_
- Component → AnotherComponent

```
<>
  <Line className="w-full h-12" />
  <AnimateLayout transitionClassName="pt-4">
    {show && <PrimaryLine key="s" className="w-full h-[80px]" />}
  </AnimateLayout>
  <Line className="w-full h-12 mt-4" />
</>
```
```
<div className="flex">
  <Square className="w-[200px] h-[200px]" />
  <AnimateLayout
    dimension="width"
    transitionClassName="pl-6"
    enter={{ delay: 200 }}
    layoutExit={{ delay: 75 }}
  >
    {show && <PrimarySquare key="s" className="w-[200px] h-[200px]" />}
  </AnimateLayout>
  <Square className="w-[200px] h-[200px] ml-6" />
</div>
```
```
<AnimateLayout
  enter={{ y: 0, delay: 150, duration: 450 }}
  exit={{ y: -8 }}
  layoutEnter={{ duration: 400 }}
>
  {open && (
    <div key="content" className="pb-4 text-secondary">
      {children}
    </div>
  )}
</AnimateLayout>
```
```
<Button
  color={recording ? "danger" : "primary"}
  size="xl"
  iconSize="lg"
  onClick={handleClick}
  loading={sending}
>
  <AnimateLayout dimension="width" transitionClassName="h-full flex items-center gap-2">
    {recording ? (
      <ArrowUp key="recording" />
    ) : (
      <Fragment key="record">
        <Wave /> Talk
      </Fragment>
    )}
  </AnimateLayout>
</Button>
```
## Props

| Name | Description | Default |
| --- | --- | --- |
| className | Class passed to wrapping elements<br>string | - |
| children\* | Components controlled by TransitionGroup rendering<br>ReactNode | - |
| as | Determines the tag used by wrapping elements<br>"div""span" | - |
| insertMethod | Determines how new children are added to the children array<br>"append""prepend" | - |
| preventInitialTransition | Determines if children should have an enter transition applied during mounting of the TransitionGroup.<br>boolean | true |
| hideOverflow | Determines if `overflow: hidden` is applied to the wrapper element<br>boolean | false |
| itemAnchor | Determines which side of the container the items will pin to during enter/exit<br>"start""end" | "\\"start\\"" |
| dimension | Determines which property will be animated during transitions<br>"width""height" | "\\"height\\"" |
| layoutEnter | LayoutTransitionDefinition | - |
| layoutExit | LayoutTransitionDefinition | - |
| layoutMove | LayoutTransitionDefinition | - |
| enter | TransitionDefinition | - |
| exit | TransitionDefinition | - |
| initial | InitialTransitionDefinition | - |
| transitionClassName | Class applied to the inner TransitionGroup<br>string | - |
| forceCompositeLayer | Applies `will-change` to force animating elements to composite layers. Use with caution!<br>boolean | false |
