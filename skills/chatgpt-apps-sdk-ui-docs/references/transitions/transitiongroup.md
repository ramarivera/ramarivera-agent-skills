# TransitionGroup

## Primitive for rendering components over time

### Usage

```
import { TransitionGroup } from "@openai/apps-sdk-ui/components/Transition"

```

### Overview

`<TransitionGroup>` manages the mounting and unmounting of components _over time_ by controlling the rendering of `children` passed to the component.

When `children` are mounted and unmounted, `<TransitionGroup>` wraps the components with a containing element and applies stateful data attributes for entering and exiting transitions.

The timing of component rendering and stateful data attributes is based on `enterDuration` and `exitDuration` values. Children must provide a stable `key` to correctly keep track of component references.

### When to use

Always reach for `<Animate>`, `<AnimateLayout>`, or `<AnimateLayoutGroup>` before using `<TransitionGroup>` directly.

Direct use of this primitive should only be necessary for very complex transitions with many moving parts.

Hide

```
// JSX
<TransitionGroup className={s.Example} enterDuration={2000} exitDuration={1000}>
  {show && <Square key="s" />}
</TransitionGroup>

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

There are two types of transitions, enter and exit, and five total data attributes that represent the possible state of transitions.

The transition data attributes are transient, only applied while they are relevant. When a given transition is completed, attribute are removed.

No styles are provided by default from `<TransitionGroup>`.

| Attribute | Description |
| --- | --- |
| `data-entering` | Component enter transition is about to start - useful for staging enter animation styles.<br>Remains applied through the entire entrance transition. |
| `data-entering-active` | Component enter transition is active. |
| `data-exiting` | Component exit transition is about to start - useful for staging exit animation styles.<br>Remains applied through the entire exit transition. |
| `data-exiting-active` | Component exit transition is active. |
| `data-interrupted` | Component was animating, but then changed to the opposite transition before the original<br>transition completed. For example, an exiting component was re-mounted again, or an entering<br>component was removed before completing entrance. |

### Initial mount transitions

By default, `<TransitionGroup>` prevents initial transitions of `children` components when it _itself_ is mounted to the DOM.

For specific situations where you want children of the `<TransitionGroup>` to transition as it's mounted, pass `preventInitialTransition={false}`.

In the above example, `<Sample>` will experience an initial enter transition when the `TransitionGroup` is rendered.

```
<TransitionGroup preventInitialTransition={false}>{show && <Sample key="s" />}</TransitionGroup>

```

### Props

| Name | Description | Default |
| --- | --- | --- |
| children\* | Components controlled by TransitionGroup rendering<br>ReactNode | - |
| as | Determines the tag used by wrapping elements<br>"div""span" | - |
| className | Class passed to wrapping elements<br>string | - |
| transitionId | Identifier passed to wrapping elements as `[data-transition-id]`<br>string | - |
| enterDuration | Determines the amount of time that the enter state is applied during mounting<br>number | - |
| exitDuration | Determines the amount of time that the exit state is applied before unmounting<br>number | - |
| preventInitialTransition | Determines if children should have an enter transition applied during mounting of the TransitionGroup.<br>boolean | true |
| enterMountDelay | Delay in MS to wait before mounting a child. `null` for no delay (default).<br>number | - |
| disableAnimations | Render children changes immediately, bypassing transition timings<br>boolean | - |
| insertMethod | Determines how new children are added to the children array<br>"append""prepend" | - |
| style | Styles applied to wrapping elements<br>CSSProperties | - |
| ref | Ref for the TransitionGroup<br>Ref<unknown> | - |
| onEnter | Callback fired when an enter animation is staged (e.g., component mounted to the DOM)<br>TransitionGroupChildCallback | - |
| onEnterActive | Callback fired when an enter animation starts<br>TransitionGroupChildCallback | - |
| onEnterComplete | Callback fired when an enter animation completes<br>TransitionGroupChildCallback | - |
| onExit | Callback fired when an exit animation is staged<br>TransitionGroupChildCallback | - |
| onExitActive | Callback fired when an exit animation starts<br>TransitionGroupChildCallback | - |
| onExitComplete | Callback fired when an exit animation completes (e.g., component unmounted from the DOM)<br>TransitionGroupChildCallback | - |

[Skip to canvas](https://openai.github.io/apps-sdk-ui/?path=/docs/transitions-transitiongroup--docs#storybook-preview-wrapper)

[![Apps SDK UI](https://openai.github.io/apps-sdk-ui/logo-storybook.svg)](https://developers.openai.com/ "Apps SDK UI")

Search for components

`⌃ K`

Overview

[Introduction](https://openai.github.io/apps-sdk-ui/?path=/docs/overview-introduction--docs)

[Installation](https://openai.github.io/apps-sdk-ui/?path=/docs/overview-installation--docs)

Concepts

[Dark mode](https://openai.github.io/apps-sdk-ui/?path=/docs/concepts-dark-mode--docs)

[Responsive design](https://openai.github.io/apps-sdk-ui/?path=/docs/concepts-responsive-design--docs)

[Typography](https://openai.github.io/apps-sdk-ui/?path=/docs/concepts-typography--docs)

Foundations

[Colors](https://openai.github.io/apps-sdk-ui/?path=/docs/foundations-colors--docs)

[Design tokens](https://openai.github.io/apps-sdk-ui/?path=/docs/foundations-design-tokens--docs)

[Icons](https://openai.github.io/apps-sdk-ui/?path=/docs/foundations-icons--docs)

Components

[Alert](https://openai.github.io/apps-sdk-ui/?path=/docs/components-alert--docs)

[Avatar](https://openai.github.io/apps-sdk-ui/?path=/docs/components-avatar--docs)

[AvatarGroup](https://openai.github.io/apps-sdk-ui/?path=/docs/components-avatargroup--docs)

[Badge](https://openai.github.io/apps-sdk-ui/?path=/docs/components-badge--docs)

[Button](https://openai.github.io/apps-sdk-ui/?path=/docs/components-button--docs)

[ButtonLink](https://openai.github.io/apps-sdk-ui/?path=/docs/components-buttonlink--docs)

[Checkbox](https://openai.github.io/apps-sdk-ui/?path=/docs/components-checkbox--docs)

[CodeBlock](https://openai.github.io/apps-sdk-ui/?path=/docs/components-codeblock--docs)

[DatePicker](https://openai.github.io/apps-sdk-ui/?path=/docs/components-datepicker--docs)

[DateRangePicker](https://openai.github.io/apps-sdk-ui/?path=/docs/components-daterangepicker--docs)

[EmptyMessage](https://openai.github.io/apps-sdk-ui/?path=/docs/components-emptymessage--docs)

[Indicators](https://openai.github.io/apps-sdk-ui/?path=/docs/components-indicators--docs)

[Input](https://openai.github.io/apps-sdk-ui/?path=/docs/components-input--docs)

[Markdown](https://openai.github.io/apps-sdk-ui/?path=/docs/components-markdown--docs)

[Menu](https://openai.github.io/apps-sdk-ui/?path=/docs/components-menu--docs)

[Popover](https://openai.github.io/apps-sdk-ui/?path=/docs/components-popover--docs)

[RadioGroup](https://openai.github.io/apps-sdk-ui/?path=/docs/components-radiogroup--docs)

[SegmentedControl](https://openai.github.io/apps-sdk-ui/?path=/docs/components-segmentedcontrol--docs)

[Select](https://openai.github.io/apps-sdk-ui/?path=/docs/components-select--docs)

[SelectControl](https://openai.github.io/apps-sdk-ui/?path=/docs/components-selectcontrol--docs)

[Slider](https://openai.github.io/apps-sdk-ui/?path=/docs/components-slider--docs)

[Switch](https://openai.github.io/apps-sdk-ui/?path=/docs/components-switch--docs)

[TagInput](https://openai.github.io/apps-sdk-ui/?path=/docs/components-taginput--docs)

[TextLink](https://openai.github.io/apps-sdk-ui/?path=/docs/components-textlink--docs)

[Textarea](https://openai.github.io/apps-sdk-ui/?path=/docs/components-textarea--docs)

[Tooltip](https://openai.github.io/apps-sdk-ui/?path=/docs/components-tooltip--docs)

Transitions

[Animate](https://openai.github.io/apps-sdk-ui/?path=/docs/transitions-animate--docs)

[AnimateLayout](https://openai.github.io/apps-sdk-ui/?path=/docs/transitions-animatelayout--docs)

[AnimateLayoutGroup](https://openai.github.io/apps-sdk-ui/?path=/docs/transitions-animatelayoutgroup--docs)

[SlotTransitionGroup](https://openai.github.io/apps-sdk-ui/?path=/docs/transitions-slottransitiongroup--docs)

[TransitionGroup](https://openai.github.io/apps-sdk-ui/?path=/docs/transitions-transitiongroup--docs) [Skip to canvas](https://openai.github.io/apps-sdk-ui/?path=/docs/transitions-transitiongroup--docs#storybook-preview-wrapper)

Recently opened

2. Docs

TransitionsTransitionGroup
