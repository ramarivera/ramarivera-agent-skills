# Select

## Choose from a dropdown of options

## Usage

```
import { Select } from "@openai/apps-sdk-ui/components/Select";

```

```
<Select
  value={fruit}
  options={fruits}
  onChange={handleChange}
  placeholder="Select a fruit..."
  variant="solid"
/>
```

## Reference

| Name | Description | Default |
| --- | --- | --- |
| onChange\* | CallbackWithOption<T> \| CallbackWithOptions<T> | - |
| options\* | Options<T> | - |
| value\* | string \| string\[\] | - |
| actions | Actions to display below the options list.<br>Actions | - |
| align | The preferred alignment against the trigger. May change when collisions occur.<br>"start""end""center" | "center" |
| alignOffset | An offset in pixels from the "start" or "end" alignment options.<br>number | 0 |
| block | Extends select to 100% of available width.<br>boolean | true |
| clearable | Display a clear action that allows the select to be unset.<br>boolean | false |
| disabled | Disables the select visually and from interactions<br>boolean | false |
| dropdownIconType | Icon displayed in the far right of the select trigger<br>"none""chevronDown""dropdown" | "dropdown" |
| id | Allows the select to be targeted with htmlFor<br>string | - |
| listMaxWidth | Defines the `max-width` property of the custom select menu, in pixels.<br>number"auto" | auto |
| listMinWidth | Defines the `min-width` property of the custom select menu, in pixels.<br>number"auto" | auto |
| listWidth | Set the width of the custom select menu<br>number"auto" | auto |
| loading | Displays loading indicator on top of button contents<br>boolean | false |
| loadingPlaceholder | Placeholder text for the select while loading. Behaves exactly like `placeholder`, and `value` will be shown if provided.<br>string | "Loading..." |
| multiple | Determines if the select should support multiple selection<br>boolean | false<br>false |
| name | Creates the ability to query the value with `[name="${name}"]`<br>string | - |
| opticallyAlign | Applies a negative margin using the current gutter to optically align the trigger<br>with surrounding content.<br>"start""end" | - |
| optionClassName | Custom class applied to option containers<br>string | - |
| OptionView | Customize the rendered output of individual options<br>NOTE: Must be passed as a stable reference, not created line.<br>FC<T> | - |
| pill | Determines if the select trigger should be a fully rounded pill shape<br>boolean | false |
| placeholder | Placeholder text for the select<br>string | "Select..." |
| required | Marks the select as a required field when using native form submission<br>boolean | - |
| searchEmptyMessage | Message displayed when search results are empty. Can be a simple string, or custom JSX.<br>ReactNode | - |
| searchPlaceholder | Placeholder of the search input<br>string | - |
| searchPredicate | Predicate used to filter searches<br>SearchPredicate<T> | - |
| side | The preferred side of the trigger to render against when open. Will be reversed when collisions occur.<br>"top""bottom" | "bottom" |
| size | Controls size of the select trigger, and several other aspects of trigger styling.

| 3xs | 2xs | xs | sm | md | lg | xl | 2xl | 3xl |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| `22px` | `24px` | `26px` | `28px` | `32px` | `36px` | `40px` | `44px` | `48px` |

| triggerClassName | Custom class applied to the select trigger<br>string | - |
| TriggerStartIcon | Icon displayed at the start of the select trigger<br>ComponentType<SVGProps<SVGSVGElement>> | - |
| TriggerView | Customize the rendered output of the trigger<br>NOTE: Must be passed as a stable reference, not created inline.<br>Customize the rendered output of the trigger<br>NOTE: Must be passed as a stable reference, not created line.<br>FC<T> \| FC<MultiSelectTriggerViewProps<T>> | - |
| variant | Style variant for the select trigger<br>"soft""outline""ghost" | "outline" |

```
const RoleOptionDescription = ({ children }: { children: React.ReactNode }) => (
  <div className="font-normal text-secondary py-px text-[0.935em] leading-[1.45]">
    {children}
  </div>
);

const roles: Role[] = [\
  {\
    value: "owner",\
    label: "Owner",\
    description: (\
      <RoleOptionDescription>\
        Can modify project information and manage project members\
      </RoleOptionDescription>\
    ),\
  },\
  {\
    value: "reader",\
    label: "Reader",\
    description: (\
      <RoleOptionDescription>\
        Can make API requests that read or modify data\
      </RoleOptionDescription>\
    ),\
  },\
];

const CustomSelect = () => (
  <Select
    value={role}
    options={roles}
    placeholder="Select role..."
    align="start"
    listMinWidth={260}
    variant="ghost"
    size="lg"
    onChange={({ value }) => setRole(value)}
    TriggerStartIcon={role === "owner" ? UserLock : User}
    triggerClassName="font-semibold"
    optionClassName="font-semibold"
  />
)
```
```
<Select
  value={value}
  onChange={handleChange}
  options={items}
  placeholder="Select..."
  align="start"
  listMinWidth={240}
  triggerClassName="font-semibold"
  actions={[\
    {\
      id: "create",\
      label: "Create project",\
      Icon: Plus,\
      onSelect: () => {},\
    },\
    {\
      id: "overview",\
      label: "Organization overview",\
      Icon: Workspace,\
      onSelect: () => {},\
    },\
  ]}
/>
```
```
const groupedItems = [\
  {\
    label: "Models",\
    options: [\
      ...\
    ],\
    // Custom limits\
    optionsLimit: {\
      limit: 7,\
      label: "Show all models",\
    },\
  },\
  {\
    label: "Fine-tunes",\
    options: [\
      ...\
    ],\
    // Default\
    optionsLimit: {\
      limit: 100,\
      label: "Show all",\
    },\
  },\
];

const GroupedOptions = () => {
  const [value, setValue] = useState<string>("");

  return (
    <Select
      value={value}
      options={groupedItems}
      onChange={(v) => setValue(v.value)}
      variant="outline"
      size="lg"
      side="bottom"
      listMinWidth={300}
      searchPlaceholder="Select a model..."
      clearable
    />
  );
};
```
```
const MultiFruitTriggerView = ({
  values,
  selectedAll,
}: {
  values: { label: string }[];
  selectedAll: boolean;
}) => {
  const displayValue = selectedAll
    ? "All fruits"
    : values.length === 1
    ? values[0].label
    : `${values.length} fruits`;

  return <>{displayValue}</>;
};

const MultiFruitSelect = () => {
  const [fruits, setFruits] = useState<string[]>([]);

  return (
    <Select
      variant="solid"
      placeholder="Select fruits..."
      options={fruitsOptions}
      name="fruits"
      multiple
      clearable
      value={fruits}
      onChange={(values) => {
          setFruits(values.map(({ value }) => value));
      }}
      TriggerView={MultiFruitTriggerView}
    />
  );
};
```
