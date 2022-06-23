# Change Log

## [3.0.0] 2022-06-24

- Renamed components name prefix from Vsud to Soft.

## [2.0.0] 2022-03-30

### Bug fixing

### Major style changes

- VsudAlert `icon` prop updated with empty default value.
- VsudAvatar `img` prop updated with `required: true` attribute.
- VsudInput `isValid` prop removed and added <code>`success`</code> and <code>`error`</code> props instead.
- VsudInput `placeholder` prop set with default value of `Type here...` .
- VsudInput `type` prop set with default value of `text`.
- VsudInput `isRequired` prop updated with default value of `false`.
- VsudPagination `color` set to default value of `success`.
- VsudPagination `size`set to default value of `md`.
- VsudButton `color` prop updated from `info` to `success` color.
- VsudCheckbox `checked` prop updated from `string` to `boolean`.
- VsudProgress `color` prop updated from `primary` to `success`.
- VsudProgress `percentage` prop is now `required` and updated from `string` to `Number`.
- VsudRadio `name`, and <code>`id`</code> props are now set to `required.`
- VsudRadio `checked` prop type changed from `string` to `boolean` and default value set to `false`.
- VsudSwitch `name`, and `id` prop values are `required` now.
- VsudSwitch `checked` prop type `changed` from `string` to `boolean`.
- VsudSwitch `inputClass` prop removed and can directly be accessed using `class`.
- VsudTextArea `id` prop is set to `required` now.
- VsudTextArea `placeholder` prop has now a default text.
- Renamed `Card` component to `MiniStatisticsCard`.
- MiniStatisticsCard `title` prop accepts `String` and `Object` with `text` and `color` keys.
- MiniStatisticsCard `value` prop accepts `Number`, `String`, and `Object` with `text`, and `color` keys.
- MiniStatisticsCard `percentage` prop accepts `String` and `Object` with `value` and `color` keys. The default `color` is set to `text-success`.
- MiniStatisticsCard `icon` prop accepts `String` and `Object` with `component` and `background` keys. The default `background` color is set to `bg-white`.
- MiniStatisticsCard `classContent` prop accepts a `string` to apply custom class around the content.
- DefaultInfoCard `classIcon` prop is renamed to `icon`.
- DefaultInfoCard `icon` prop can accept a `String` or `Object` with `component` and `background` keys.
- DefaultInfoCard `title` prop’s value is set to `required`.
- DefaultInfoCard `price` prop is renamed to `value` with the acceptable types of `String`, and `Number`.
- MasterCard `props` refactored to a single `card` object prop with the following keys:
  - `number` accepts a `String` with the default value of `7852 4594 1122 4562`.
  - `holderText` accepts a `String` with the default value of `Card Holder`.
  - `holderName` accepts a `String` with the default value of `Jack Peterson`.
  - `expiryText` accepts a `String` with the default value of `Expirs`.
  - `expiryDate` accepts a `String` with the default value of `11/22`.
  - `background` accepts a `String` with the default value of `dark`.
- Added `MiniPlayerCard` component with `color`, and `song` props.
- Renamed `NewTabCard` to `PlaceHolderCard`.
- Added `icon`, and `title` prop type of object with `variant` and `text` keys to PlaceholderCard.
- Deleted `TransactionsCard` and `RevenueCard` components and added new `RankingList` and `RankingListCard` component instead.
- Added `card` object prop with `title`, `subtitle`, `date` keys to `RankingListCard` component.
- Added boolean `HorizontalBreak` and array `item` props with `title`, `date`, `amount`, `icon`, `color` keys to `RankingListCard` component.
- Added `id`, `height`, `title`, `description` and `chart` props to `GradientLineChart`. The `chart` has `Object` data type with the following keys:
  - `labels` has `Array` data type.
  - `datasets` has `Array` data type with the following keys:
    - `label` has `String` data type.
    - `data` has `Array` data type.
- Renamed `ActiveUsersChart` component to `ReportsBarChart`.
- Added Added `id`, `color`, `title`, `description`, `chart`, and `items` props to `ReportsBarChart`. The `items` prop has `Array` data type and the `chart` has `Object` data type with the following keys:
  - `labels` has `Array` data type.
  - `datasets` has `Object` data type with the following keys:
    - `label` has `String` data type.
    - `data` has `Array` data type.
- Updated `BillingCard` with the `title` and `bills` props.
- Renamed `CardCalendar` component to `CalendarCard` component and added `items` prop type of array with `time` and `description` keys.
- Renamed `ProjectOverviewCard` component to `DefaultProjectCard` component and added the following props: `image`, `label`, `title`, `description`, `action`, and `authors` props.
- Renamed `CardEmail` component to `EmailCard` component and Added `route`, `text`, and `tooltip` props.
- Renamed `CardMessage` component to `MessageCard` component.
- Added `title`, and `messages` prop type of array with the `route`, `tooltip`, and `images` keys to MessageCard.
- Renamed `PaymentCard` component to `PaymentMethodsCard` component.
- Renamed `ProfileCard` component to `ProfileInfoCard` and added the following props: `title`, `description`, `info`, `social`, and `action`.
- Deleted `TimelineCard` component and added `TimelineList` and `TimelineItem` components.
- Added `title`, `description` and `darkMode` props to TimelineList component.
- Added `color`, `icon`, `title`, `dateTime`, `description`, `badges`, and `darkMode` props to TimelineItem component.
- Renamed `CardToDo` component to `TodoCard` component.
- Added `todos` prop to `TodoCard` component.

### Deleted components

```
@/components/Icon.vue
```

### Added components

```
@/components/Icon/Air.vue
@/components/Icon/Basket.vue
@/components/Icon/Box3d.vue
@/components/Icon/CreditCard.vue
@/components/Icon/CustomerSupport.vue
@/components/Icon/Document.vue
@/components/Icon/GettingStarted.vue
@/components/Icon/Humidity.vue
@/components/Icon/Lights.vue
@/components/Icon/Office.vue
@/components/Icon/Settings.vue
@/components/Icon/Shop.vue
@/components/Icon/Spaceship.vue
@/components/Icon/Switches.vue
@/components/Icon/Temperature.vue
@/components/Icon/Wifi.vue

```

### Deleted dependencies

### Added dependencies

```
@fortawesome/vue-fontawesome
```

### Updated dependencies

### Warning

## [1.0.0] 2022-01-27

### Initial Release
