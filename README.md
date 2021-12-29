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

import IpengWatermark from "@ipeng-watermark"

export default {
  components:{
    IpengWatermark
  }
}

```

## Properties:

#### el
Type: String
Default: 'body'

A selector, the watermark layer will be inserted into this element.

#### txt
Type: String
Default: 'ipeng-watermark'

Watermark's content.

#### color
Type: String
Default: '#d9d9d9'

Watermark's color.

#### size
Type: Number
Default: 18
Watermark's fontsize.

#### opacity
Type: Number
Default: 0.7
Range: 0~1

Watermark's opacity.

#### zIndex
Type: Number
Default: 0

The level of watermark layer.




