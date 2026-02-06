# Animate

## Animate components as they mount and unmount

### Usage

```
import { Animate } from "@openai/apps-sdk-ui/components/Transition"

```

### Overview

`<Animate>` is an abstraction around `<TransitionGroup>` for batteries-included transition animations.

`enter`, `exit`, and `initial` props allow you to define the behavior of the animation from a set of GPU-accelerated properties. Animatable properties include `opacity`, `x`, `y`, `scale`, `rotate`, `skewX`, `skewY`, and `blur`.

### When to use

`<Animate>` is great for transitions that don't need to affect the layout of surrounding DOM nodes. Typically, this will mean components with a fixed size or `absolute` positioning.

These animations should be for transitioning between two states that occupy _the same space_, such as:

- _nothing_ → Component
- Component → _nothing_
- Component → AnotherComponent

```
<Animate className="w-[200px] h-[200px]">
  {visible && <Square key="s" />}
</Animate>
```
```
<Animate
  className="w-[200px] h-[200px]"
  enter={{ scale: 1 }}
  exit={{ scale: 0.5, blur: 20 }}
>
  {visible && <Square key="s" />}
</Animate>
```
```
<Animate
  className="w-[200px] h-[200px]"
  initial={{ x: 120, skewX: 30 }}
  enter={{ duration: 800 }}
  exit={{ x: -120, skewX: -8, duration: 500 }}
>
  {visible && <Square key="s" />}
</Animate>
```
```
<Button size="2xl" iconSize="xl" variant="soft" onClick={handleClick}>
  <Animate
    className="w-[var(--button-icon-size)] h-[var(--button-icon-size)]"
    enter={{ scale: 1, delay: 150, duration: 400 }}
    exit={{ scale: 0.6, duration: 150 }}
  >
    {copied ? <Check key="copied" /> : <Copy key="copy" />}
  </Animate>
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
| transitionClassName | Class applied to the inner TransitionGroup<br>string | - |
| enter | Styles applied to the enter transition<br>TransitionDefinition | - |
| exit | Styles applied to the exit transition<br>TransitionDefinition | - |
| initial | Styles applied before the enter transition occurs<br>InitialTransitionDefinition | - |
| transitionPosition | Determines how transition states are positioned<br>"static""absolute" | "absolute" |
| forceCompositeLayer | Applies `will-change` to force animating elements to composite layers. Use with caution!<br>boolean | false |
