<template>
  <div class="detail">
    <div class="banner" :style="colorStyle" >
    </div>
    
  </div>
</template>

<script>
export default {
  name: 'SectionPlain',
  props: ['color'],
  computed:{
   
    colorStyle(){
      return {background: this.color}
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.detail{
  
  display: block;
  height: 300px;  
  margin: auto;
}




</style>
