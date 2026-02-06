# Indicators

## Display loading and progress states to users

## `LoadingIndicator`

Simple spinning indicator for general loading states.

### Usage

```
import { LoadingIndicator } from "@openai/apps-sdk-ui/components/Indicator";

<LoadingIndicator size={24} />
```

### Reference

| Name | Description | Default |
| --- | --- | --- |
| size | Size of the indicator, in pixels<br>stringnumber | 1em |
| className | Classname applied to the indicator<br>string | - |
| strokeWidth | Stroke width of the indicator, in pixels<br>number | 2 |

### Sizing & stroke

By default, the indicator adapts to the surrounding `font-size` and `color` of text.

You can control the size of the `LoadingIndicator` using the `--indicator-size` CSS custom property.

```
<LoadingIndicator
  size={30}
  strokeWidth={2}
/>
```

| Name | Description | Default | Control |
| --- | --- | --- | --- |
| size | Size of the indicator, in pixels<br>stringnumber | 1em | 1030 / 50 |
| strokeWidth | Stroke width of the indicator, in pixels<br>number | 2 | 12 / 10 |

### Color

The indicator defaults to `currentcolor`, inheriting the surrounding text color. This can also be customized by altering the `--indicator-color` variable around the DOM scope of the component.

Destroying forever...

```
<div className="flex items-center gap-2 text-danger">
  <LoadingIndicator />
  Destroying forever...
</div>
```

### Duration

You can control the rotation speed of the spinner with `--indicator-rotate-duration`.

```
<div
  style={{
    '--indicator-rotate-duration': '3s'
  }}
>
  <LoadingIndicator />
</div>
```

* * *

## `CircularProgress`

Circular progress ring with simulated progress animation.

### Usage

```
import { CircularProgress } from "@openai/apps-sdk-ui/components/Indicator";

<CircularProgress />
```

### Progress

Use `progress` to define a static progress and prevent the animation.

```
<CircularProgress progress={25} />
```

### Sizing & stroke

Use `size` and `strokeWidth` to control the sizing and thickness of the loader.

You can also control these values with CSS variables by targeting `--circular-progress-size` and `--circular-progress-stroke`.

```
<o
  size={30}
  strokeWidth={2}
/>
```

| Name | Description | Default | Control |
| --- | --- | --- | --- |
| size | Size of the indicator, in pixels<br>stringnumber | 1em | 1030 / 50 |
| strokeWidth | Stroke width of the indicator, in pixels<br>number | 2 | 12 / 4 |

### Color

Customize the color of the indicator with the `--circular-progress-track-color` and `--circular-progress-track-active-color` variables.

```
<o
  trackActiveColor="var(--gray-1000)"
  trackColor="var(--alpha-15)"
/>
```

* * *

## `LoadingDots`

Indicate typing progress with staggered pulsing dot animation.

### Usage

```
import { LoadingDots } from "@openai/apps-sdk-ui/components/Indicator";

<LoadingDots />
```

### Color

The indicator defaults to `currentcolor`, inheriting the surrounding text color.

You can customize the color by providing a different `color` value or context.

```
<LoadingDots className="text-danger" />
```
