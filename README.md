# react-native-collapsible-view

_Animated collapsible view component for React Native based on [react-native-collapsible](https://github.com/oblador/react-native-collapsible)_

## Overview

A simple component of a common use case of collapsible - a visible title with a collapsible view beneath it.

#### main features

- arrow animation indicating whether the collapsible is expanded or not.
- unmountOnCollapse property which unmount the collapsible when it is not expanded(can be very useful when considering performance of a page with multiple collapsible views).
- support both RTL and LTR languages(if not specified, default direction based on the device language is chosen).
- state can be managed by other component(controlled) or independently(uncontrolled).
- super simple API but yet customizable.
- supported both on Android and iOS.

## Demo

### gif

<!-- ![collapsible-view](https://user-images.githubusercontent.com/47307889/90984281-9d8a1880-e57c-11ea-9c59-bba46df80f90.gif) -->

![collapsible-view2](https://user-images.githubusercontent.com/47307889/91665613-865ca500-eaff-11ea-91bd-ef3c5a25fb7d.gif)

### Snack

play live on Snack!
https://snack.expo.io/@eliav2/78bcb7

## Installation

```bash
$ npm install @eliav2/react-native-collapsible-view

// or with yarn
$ yarn add @eliav2/react-native-collapsible-view
```

## Simple Usage

```js
import React from "react";
import { Text } from "react-native";
import CollapsibleView from "@eliav2/react-native-collapsible-view";

export default () => {
  return (
    <CollapsibleView title="Simple collapsible">
      <Text>hey there!</Text>
    </CollapsibleView>
  );
};
```

## Properties

#### title

can be string, or jsx element. in case of string a default styling is chosen.
examples:

- `title={"Cool View"}`
- `title={<Text style={{ color: "red", fontSize: 36, fontStyle: "italic" }}>Custom Styling</Text>}`

default value: `title=''`

#### expanded

use this property to control the collapsible state by his parent(or some other component). if a value for expanded is given(true or false) - then his state is managed by his parent only(pressing on the collapsible directly will not toggle his state).
if given - the collapsible considered as `controlled`(by other component),if not, the collapsible is `uncontrolled`(default).
examples:

- `expanded={true}`

default value: `expanded = {null}`

#### initExpanded

if true then the collapsible will be expanded on mounting.
makes a difference only when uncontrolled.
examples:

- `initExpanded={true}`

default value: `initExpanded = {false}`

#### unmountOnCollapse

if true then the collapsible(beneath the title) will unmount when closing animation ends.
can be very useful when considering performance! use wisely!
examples:

- `unmountOnCollapse={true}`

default value: `unmountOnCollapse = {false}`

#### isRTL

can be true or false.
set `isRTL=true` is your language is arabic or hebrew(text writing direction is RTL).
if not specified, default direction based on the device language is chosen.
Note - if you specify direction, the component will force that direction, means that if you provided `isRTL=true` but device language is not RTL language then the flexDirection will be flipped from 'row' to 'row-reverse' so the view will look good.
examples:

- `isRTL={true}`

default value: `isRTL = "auto"`

#### duration

sets the animation duration of both collapsible element and the arrow rotation.
examples:

- `duration = 4000`

default value: `duration = {300}`

#### collapsibleProps

Object - This properties will be passed down to the [collapsible](https://github.com/oblador/react-native-collapsible) element.
[These are](https://github.com/oblador/react-native-collapsible#properties) the available properties.
examples:

- `collapsibleProps={{ onAnimationEnd: () => alert("animation ended") }}`

default value: `collapsibleProps = {{}}`

#### arrowSize

set ths size of the arrow.
examples:

- `arrowSize = {48}`

default value: `arrowSize = {24}`

#### noArrow

if set to true the arrow indicating whether the collapsible-view is expanded or not will not be displayed.
examples:

- `noArrow = {true}`

default value: `noArrow = {false}`

#### style

give custom style to the view containing the collapsible(the container).
examples:

- `style={{ borderWidth: 0, backgroundColor: "#6495ED" }}`

default value: `style={{}}`
