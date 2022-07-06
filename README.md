# React Native - Animated Searchbox

A simple search box with animation. Compatible with Expo CLI and React Native CLI.

- Easy to use,
- Lightweight, fast, flexible and easy customizable,
- Support both IOS & Android Devices,
- Also Support React Native Web

## Install

We used a search SVG icon in this project.  
So, you need to install the [React Native SVG](https://github.com/react-native-community/react-native-svg#installation) library before continue the installation.

After that;

```
npm install @ocean28799/react-native-animated-searchbox --save

--- OR ---

yarn add @ocean28799/react-native-animated-searchbox
```

## Demo

|![SCREENSHOT](https://raw.githubusercontent.com/gurayyarar/React-Native-Animated-Searchbox/HEAD/assets/demo/web.gif)|

## Usage

```javascript
import React, { useRef } from "react";
import AnimatedSearchBox from "@ocean28799/react-native-animated-searchbox";

export default function Demo() {
  const refSearchBox = useRef();
  //Call for the open
  const openSearchBox = () => refSearchBox.current.open();

  //Call for the close
  const closeSearchBox = () => refSearchBox.current.close();

  return (
    <View style={{ width: "100%" }}>
      <AnimatedSearchBox
        ref={(ref) => (refSearchBox.current = ref)}
        placeholder={"Search"}
        placeholderTextColor="#848484"
        backgroundColor="#f6f6f7"
        searchIconColor="#000"
        focusAfterOpened
        searchIconSize={18}
        borderRadius={12}
        onChangeText={(text) => {
          console.log("Input: ", text);
        }}
        onBlur={() => closeSearchBox()}
      />
    </View>
  );
}
```

## Properties

| Key                  | Description                                                                          | Value Type                   | Is Required | Default                |
| -------------------- | ------------------------------------------------------------------------------------ | ---------------------------- | ----------- | ---------------------- |
| height               | Height of the search box                                                             | `number`                     | false       | 48                     |
| borderRadius         | Border radius of the search box                                                      | `number`                     | false       | 48                     |
| fontSize             | Font size of the search box                                                          | `number`                     | false       | 20                     |
| backgroundColor      | Background color of the search box                                                   | `color codes (hex,rgb,rgba)` | false       | rgba(255,255,255,0.70) |
| placeholderTextColor | Placeholder text color                                                               | `color codes (hex,rgb,rgba)` | false       | #555555                |
| searchIconSize       | Search icon width and height size                                                    | `number`                     | false       | 20                     |
| searchIconColor      | Search icon color                                                                    | `color codes (hex,rgb,rgba)` | false       | #555555                |
| focusAfterOpened     | If true, keyboard will show after search box opened                                  | `boolean`                    | false       | false                  |
| shadowColor          | Box\-shadow color of the search box\. If you don't want to please type `transparent` | `color codes (hex,rgb,rgba)` | false       | rgba(0,0,0,0.12\)      |
| placeholder          | Placeholder text of the search box                                                   | `string/text`                | true        |                        |
| animationSpeed       | Animation speeds as miliseconds                                                      | `array ([number, number])`   | false       | [200, 250]             |

And also supporting props all of the [TextInput Component of React Native](https://reactnative.dev/docs/textinput).

## Events

| Key       | Description                          |
| --------- | ------------------------------------ |
| onOpening | Trigger on search box start to open  |
| onClosing | Trigger on search box start to close |
| onOpened  | Trigger on search box fully opened   |
| onClosed  | Trigger on search box fully closed   |

And also supporting events all of the [TextInput Component of React Native](https://reactnative.dev/docs/textinput).

## License

**React Native - Animated Searchbox** is an open source project that is licensed under the [MIT license](http://opensource.org/licenses/MIT).
