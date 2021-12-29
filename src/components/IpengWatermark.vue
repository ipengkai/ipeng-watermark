<template>
  <teleport :to='el' >
    <div ref="waterCover"></div>
  </teleport>
</template>

<script>
export default {
  name: 'IpengWatermark',
  props: {
    el: String,
    txt:{
      type: String,
      default(){
        return "ipeng-watermark"
      }
    },
    color:{
      type: String,
      default(){
        return "#f2f2f2"
      }
    },
    opacity:{
      type: Number,
      default(){
        return .7;
      }
    },
    rotate:{
      type: Number,
      default(){
        return 45;
      }
    }
  },
  mounted(){
    
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

</style>
