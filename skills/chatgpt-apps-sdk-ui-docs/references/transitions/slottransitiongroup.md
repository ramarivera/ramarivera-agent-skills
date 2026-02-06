# SlotTransitionGroup

## Primitive for rendering components over time (slot-based)

### Usage

```
import { SlotTransitionGroup } from "@openai/apps-sdk-ui/components/Transition"

```

### Overview

`<SlotTransitionGroup>` manages the mounting and unmounting of components over time by applying stateful data attributes directly to the original child element(s). No wrapper elements are introduced.

When keyed `children` are mounted or unmounted, `<SlotTransitionGroup>` adds transition state data attributes on the child node itself.

The timing of stateful attributes is controlled with `enterDuration` and `exitDuration`. Children must provide a stable `key` so transitions are tracked correctly.

### When to use

- Prefer `<Animate>`, `<AnimateLayout>`, or `<AnimateLayoutGroup>` first.
- Use `<SlotTransitionGroup>` when you need `<TransitionGroup>`-like control but without any extra wrapper nodes.

Hide

```
// JSX
<SlotTransitionGroup enterDuration={2000} exitDuration={1000}>
  {show && <Square key="s" className={s.Example} />}
</SlotTransitionGroup>

// CSS
.Example {
  &[data-entering] {
    opacity: 0;
  }

  &[data-exiting] {
    opacity: 1;
  }

  &[data-entering-active],
  &[data-exiting][data-interrupted] {
    opacity: 1;
    box-shadow: 0 0 0 5px green;
    transition: opacity 2s ease, box-shadow 2s ease;
  }

  &[data-exiting-active],
  &[data-entering][data-interrupted] {
    opacity: 0;
    box-shadow: 0 0 0 5px red;
    transition: opacity 1s ease, box-shadow 1s ease;
  }
}
```

### Transition states

There are two types of transitions, enter and exit, and five total data attributes that represent the possible state of transitions. These attributes are applied directly on the child elements.

The attributes are transient and removed when no longer relevant.

No styles are provided by default.

| Attribute | Description |
| --- | --- |
| `data-entering` | Component enter transition is staged. Remains applied through the entire entrance transition. |
| `data-entering-active` | Component enter transition is active. |
| `data-exiting` | Component exit transition is staged. Remains applied through the entire exit transition. |
| `data-exiting-active` | Component exit transition is active. |
| `data-interrupted` | Component was animating and then switched to the opposite transition before completion. |

### Initial mount transitions

By default, `<SlotTransitionGroup>` prevents initial transitions of `children` when it is mounted.

If you want children to transition on the initial mount of the group, pass `preventInitialTransition={false}`.

```
<SlotTransitionGroup preventInitialTransition={false}>{show && <Sample key="s" />}</SlotTransitionGroup>

```

### Props

| Name | Description | Default |
| --- | --- | --- |
| children\* | Components controlled by SlotTransitionGroup rendering<br>ReactNode | - |
| enterDuration | Determines the amount of time that the enter state is applied during mounting<br>number | - |
| exitDuration | Determines the amount of time that the exit state is applied before unmounting<br>number | - |
| preventInitialTransition | Determines if children should have an enter transition applied during mounting of the group.<br>boolean | true |
| enterMountDelay | Delay in MS to wait before mounting a child. `null` for no delay (default).<br>number | - |
| disableAnimations | Render children changes immediately, bypassing transition timings<br>boolean | - |
| insertMethod | Determines how new children are added to the children array<br>"append""prepend" | - |
| ref | Ref for the SlotTransitionGroup (applied to the single child when possible)<br>Ref<unknown> | - |
| onEnter | Callback fired when an enter animation is staged (e.g., component mounted to the DOM)<br>TransitionGroupChildCallback | - |
| onEnterActive | Callback fired when an enter animation starts<br>TransitionGroupChildCallback | - |
| onEnterComplete | Callback fired when an enter animation completes<br>TransitionGroupChildCallback | - |
| onExit | Callback fired when an exit animation is staged<br>TransitionGroupChildCallback | - |
| onExitActive | Callback fired when an exit animation starts<br>TransitionGroupChildCallback | - |
| onExitComplete | Callback fired when an exit animation completes (e.g., component unmounted from the DOM)<br>TransitionGroupChildCallback | - |
