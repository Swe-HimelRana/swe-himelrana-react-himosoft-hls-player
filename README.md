# react-himosoft-hls-player

A custom react hls player.

It's simple and perfect for your application. 

(It's a small working part as public version of my main project)

## Introduction

`react-himosoft-hls-player` is a simple HLS live stream player.
It uses [hls.js](https://github.com/video-dev/hls.js) to play your hls live stream if your browser supports `html 5 video` and `MediaSource Extension`.

```javascript
npm install @swe-himelrana/react-himosoft-hls-player
```

## Examples

### Using the HimosoftPlayer component

```javascript
import React from "react";
import ReactDOM from "react-dom";
import {HimosoftPlayer} from "@swe-himelrana/react-himosoft-hls-player";

ReactDOM.render(
  <HimosoftPlayer
    src="https://test-streams.mux.dev/x36xhzz/x36xhzz.m3u8"
    autoPlay={false}
  />,
  document.getElementById("app")
);
```

### Using hlsConfig (advanced use case)

All available config properties can be found on the [Fine Tuning](https://github.com/video-dev/hls.js/blob/master/docs/API.md#fine-tuning) section of the Hls.js API.md

```javascript
import React from "react";
import ReactDOM from "react-dom";
import {HimosoftPlayer} from "@swe-himelrana/react-himosoft-hls-player";

ReactDOM.render(
  <HimosoftPlayer
    src="https://test-streams.mux.dev/x36xhzz/x36xhzz.m3u8"
    hlsConfig={{
      maxLoadingDelay: 4,
      minAutoBitrate: 0,
      lowLatencyMode: true,
    }}
  />,
  document.getElementById("app")
);
```

## Props

All [video properties](https://www.w3schools.com/tags/att_video_poster.asp) are supported and passed down to the underlying video component

| Prop                     | Description                                                                                                             |
| ------------------------ | ----------------------------------------------------------------------------------------------------------------------- |
| src `String`, `required` | The hls url that you want to play                                                                                       |
| autoPlay `Boolean`       | Autoplay when component is ready. Defaults to `false`                                                                   |
| hlsConfig `Object`       | `hls.js` config, you can see all config [here](https://github.com/video-dev/hls.js/blob/master/docs/API.md#fine-tuning) |
| width `String`           | Determines the width of the video player. note that if you leave this empty the video player is responsive.             |
| title `String`           | give the video a title and it will appear in the video player.                                                          |
| color `String`           | give the video player a color and it will change the color theme of the player.                                         |

### Additional Notes

By default, the HLS config will have `enableWorker` set to `false`. There have been issues with the HLS.js library that breaks some React apps, so I've disabled it to prevent people from running in to this issue. If you want to enable it and see if it works with your React app, you can simply pass in `enableWorker: true` to the `hlsConfig` prop object. [See this issue for more information](https://github.com/video-dev/hls.js/issues/2064)


# Change log of react-himosoft-hls-player

Version: 1.0.0

    - Initial Release

Version: 1.0.1

    - Simple Bug Fix

Version: 1.0.2

    - Docs update (Fixed Wrong import instruction)

Version: 1.0.3

    - Fixed minor bug

Version: 1.0.4

    - Updated Doc (Added changelog in main doc)