## Show Cases

> Zoom while sliding

![3.gif](https://cloud.githubusercontent.com/assets/7970947/18501092/87d5efe8-7a80-11e6-9234-516b2be1e729.gif)

> Intelligent zoom

![2.gif](https://cloud.githubusercontent.com/assets/7970947/18501091/87b14d8c-7a80-11e6-904d-8c434e1904ce.gif)

## Getting Started

### Installation

```bash
npm i react-native-image-pan-zoom --save
```

### Basic Usage

- Install create-react-native-app first

```bash
$ npm install -g create-react-native-app
```

- Initialization of a react-native project

```bash
$ create-react-native-app AwesomeProject
```

- Then, edit `AwesomeProject/App.js`, like this:

```typescript
import { Image, Dimensions } from 'react-native';
import ImageZoom from 'react-native-image-pan-zoom';

export default class App extends React.Component {
    render: function() {
        return (
            <ImageZoom cropWidth={Dimensions.get('window').width}
                       cropHeight={Dimensions.get('window').height}
                       imageWidth={200}
                       imageHeight={200}>
                <Image style={{width:200, height:200}}
                       source={{uri:'http://v1.qzone.cc/avatar/201407/07/00/24/53b9782c444ca987.jpg!200x200.jpg'}}/>
            </ImageZoom>
        )
    }
}
```

### Document

| Props | Type | Description | DefaultValue
| ------ | ----------- | ----------- | ----------- |
| **cropWidth(required)** | number | operating area width | 100 |
| **cropHeight(required)** | number | operating area height | 100 |
| **imageWidth(required)** | number | picture width | 100 |
| **imageHeight(required)** | number | picture height | 100 |
| onClick | ()=>void | onClick | ()=>{} |
| panToMove | boolean | allow to move picture with one finger | true |
| pinchToZoom | boolean | allow scale with two fingers | true |
| clickDistance | number | how many finger movement can also trigger `onClick`  | 10 |
| horizontalOuterRangeOffset | (offsetX?: number)=>void | horizontal beyond the distance, the parent to do picture switching, you can listen to this function. When this function is triggered, you can do the switch operation | ()=>{} |
| onDragLeft | ()=>void | trigger to switch to the left of the graph, the left sliding speed exceeds the threshold when triggered | ()=>{} |
| responderRelease | (vx: number)=>void | let go but do not cancel | ()=>{} |
| maxOverflow | number | maximum sliding threshold | 100 |
| longPressTime | number | long press threshold | 800 |
| onLongPress | ()=>void | on longPress | ()=> {} |
| doubleClickInterval | number | time allocated for second click to be considered as doublClick event | 175 |
| onMove | (object)=>void | reports movement position data (helpful to build overlays) | ()=> {} |
| isPanning | (boolean)=>void | reports whether or not a user is panning whilst zoomed (useful for disabling scrollviews) | ()=> {} |
| centerOn | { x: number, y: number, scale: number, duration: number } | if given this will cause the map to pan and zoom to the desired location | undefined

## Development pattern

### Step 1, run TS listener

After clone this repo, then:

```bash
npm install
npm start
```

### Step 2, run demo

```bash
cd demo
npm install
npm start
```

Then, scan the QR, use your [expo app](https://expo.io./). 