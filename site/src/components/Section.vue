<template>
  <div class="section" :class="{left: isLeft, right:isRight}">
    <div class="banner" >      
      
    </div>
    <div class="content">
        <slot>default</slot>
      </div>    
    
  </div>
</template>

<script>
export default {
  name: 'ArrowSection',
  props: ['direction'],
  computed:{
    isLeft(){
      return this.direction == 'left';
    },
    isRight(){
      return !this.isLeft
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.section{
  position: relative;
  display: block;
  height: 1000px;
  
}

.section.left{
  left: 0vw;
}

.section.right{
  left: 100vw;
  
}


.banner{  
  position:relative;
  background: red;
  width: 350px;
  height: 350px;
  box-shadow: 10px 10px 1px 1px black;
  border-radius: 25px;  
}

.left .banner{
  left:-200px;
}

.right .banner {
  left:-200px;
}


.section.left .banner{
  transform: scale(4, 1) rotate(45deg);
}

.section.right .banner{
  transform: scale(4, 1) rotate(-45deg);
}

.content{
  font-size: 24px;
  position: relative;
}

.section.left .content{  
  text-align: left;
  left: 100px;
  top: -250px;
  
}

.section.right .content{
  text-align: right;

  left: -1400px;
  top: -250px;
}
</style>
