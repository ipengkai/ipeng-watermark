<template>
  <teleport :to='el' >
    <div class="watermark-cover" id="ipengWatermarkCover" ></div>
  </teleport>
</template>

<script>
export default {
  name: 'ipeng-watermark',
  props: {
    el: {
      type: String,
      default(){
        return 'body'
      }
    },
    txt:{
      type: String,
      default(){
        return "ipeng-watermark"
      }
    },
    color:{
      type: String,
      default(){
        return "#d9d9d9"
      }
    },
    opacity:{
      type: Number,
      default(){
        return .7;
      }
    },
    size:{
      type: Number,
      default(){
        return 18
      }
    },
    zIndex:{
      type: Number,
      default(){
        return 0;
      }
    },
    // rotate:{
    //   type: Number,
    //   default(){
    //     return -15;
    //   }
    // }
  },
  data(){
    return {
      rotate: -20,
    }
  },
  mounted(){
    // this.createImg();
    this.addCoverBg();
  },
  methods:{
    createImg(){
      const canvas = document.createElement('canvas');
      const { size, txt, color, opacity, rotate } = this;

      canvas.style.backgroundColor = 'transparent';
      const ctx = canvas.getContext('2d');
      ctx.imageSmoothingEnabled = true;
      ctx.mozImageSmoothingEnabled = true;
      ctx.webkitImageSmoothingEnabled = true;
      ctx.msImageSmoothingEnabled = true;

      const h = size*6;
      const txtSize = ctx.measureText(txt);
      const w = txtSize.width + 60;
      canvas.width = w;
      canvas.height = h;
      // 绘制文本
      const font = `normal normal bold ${size}px/${h}px serif`;
      ctx.font = font;
      ctx.textAlign = 'center';
      ctx.textBaseline = 'middle';
      ctx.globalAlpha = opacity;

      ctx.translate(w/2, h/2);
      ctx.rotate((rotate/180)*(Math.PI));

      ctx.fillStyle = color;
      ctx.fillText(txt, 0, 0);
      ctx.restore();

      // const cover = document.querySelector("#ipengWatermarkCover");
      // cover.appendChild(canvas)
      // 将canvas转base64
      const img = canvas.toDataURL("image/png");
      return img;
    },

    addCoverBg(){
      const cover = document.querySelector("#ipengWatermarkCover");
      const img = this.createImg();

      cover.setAttribute('style',`
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        overflow: hidden;
        background-color: transparent;
        pointer-events: none;
        background-repeat: repeat;
        background-origin: center center;
        background-image: url(${img});
        Z-index: ${this.zIndex};
      `)
      
      // cover.style.backgroundImage = `url(${img})`;
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.watermark-cover{
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  overflow: hidden;
  background-color: transparent;
  pointer-events: none;
  background-repeat: repeat;
  background-origin: center center;
  // background-size: 60% ;
}
</style>
