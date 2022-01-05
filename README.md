# ipeng-watermark

## Introduction:
A watermark component based on vue3

## Installation:
```
npm i -S ipeng-watermark
```

##  Typical use:
``` html
<template>
...
<div id="box"></div>

<ipeng-watermark el="#box" txt="watermark"></ipeng-watermark>
...
</template>
```

``` js

import IpengWatermark from "ipeng-watermark"

export default {
  components:{
    IpengWatermark
  }
}

```

## Properties:

### el
Type: String<br>
Default: 'body'<br>

A selector, the watermark layer will be inserted into this element. 

Notice: This element must has a positioning property ( relative/absolute/fixed ), and the ipengWatermark component cannot be its child element!

### txt
Type: String<br>
Default: 'ipeng-watermark'<br>

Watermark's content.

### color
Type: String<br>
Default: '#d9d9d9'<br>

Watermark's color.

### size
Type: Number<br>
Default: 18<br>
Watermark's fontsize.

### opacity
Type: Number<br>
Default: 0.7<br>
Range: 0~1<br>

Watermark's opacity.

### xGap
Type: Number<br>
Default: 60<br>

Horizontal spacing between two watermarks

### yGap
Type: Number<br>
Default: 90<br>

Vertical spacing between two watermarks

### zIndex
Type: Number<br>
Default: 0<br>

The level of watermark layer.




