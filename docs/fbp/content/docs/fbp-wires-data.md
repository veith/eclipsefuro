---
title: Wire Data
weight: 10
---


# Data on wires
Wires are not limited to triggering something, they also transport information.

{{< hint info >}}
**Note**

By default the content of  **EVENT.detail** is passed to the target. If an event does not have a detail property, the 
receiver will get a `undefined`. 

  {{< /hint >}}

## Passing useful data to target

<furo-demo-snippet flow>
<template>
  <furo-color-input label="choose a color"  @-value-changed="--newColor"></furo-color-input> 
  <light-bulb on  ƒ-set-color="--newColor"></light-bulb>
</template>
</furo-demo-snippet>

*The color picker dispatches a `value-changed` event, with the color as payload.*

 

## Send the complete *event* instead of *event.detail*
You can put the complete *event* or any *sub.property* of the event on the wire by defining the details
at the producer / triggerer.

### Producer (@-)
You can define exactly what you want to put on the wire on the producing side.

- **@-event="--wireName(*)"** will send the complete event.
- **@-event="--wireName(*.key)"** will send the property key of the event.


### Receiver (ƒ-)
You can pass a subset of the data on a wire to a receiver.

- **ƒ-doit="--wireName(*.title)"** will call `doit(wiredata.title)`on the receiver.
- **ƒ-doit="--wireName(*.page.2.title)"** will call `doit(wiredata.page[2].title)` on the receiver with checks that index 2 and the sub property really exist.


## Storing event data on a class member property  (aka parking)

Sometimes you want to store data for later usage. To store data from an event 
write the property that you want to update in a double bracket  `((targetProperty))`.

- **@-value-changed="((color1))** will update the component property `color1` with the value of `EVENT.detail`.


{{< hint danger >}}
**Note**

Keep in mind that you will overwrite existing properties of your host. A name like shadowRoot can cause problems.
{{< /hint >}}


<furo-demo-snippet flow style="height:200px">
<template>
  <!-- the color input will store the value on the varable color -->
  <furo-color-input label="choose color 1"  @-value-changed="((color))"></furo-color-input>
</template>
</furo-demo-snippet>

*Look at the example below to see how you can use parked data*

## Sending host member properties with events
To send parked data, write the property name in brackets after the wire. 

- **@-click="--newColor(color1)"** will put the value of `color1` on the wire `--newColor` instead of the detail value of the click event.


<furo-demo-snippet flow style="height:300px">
<template>
  <!-- the color input will store the value on the varable color -->
  <furo-color-input label="choose color 1"  @-value-changed="((color))"></furo-color-input>
  <!-- the button will put the value of color on the wire --newColor -->
  <furo-button @-click="--newColor(color)" label="setColor"></furo-button>
  <light-bulb ƒ-set-color="--newColor" on></light-bulb>
</template>
</furo-demo-snippet>

