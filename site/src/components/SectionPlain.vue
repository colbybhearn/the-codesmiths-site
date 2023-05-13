<template>
  <div class="section" :class="{left: isLeft, right:isRight}" >
    
    <div class="wrapper" >
      <div class="banner" :style="style" @click="toggle">
      </div>
      <div style="display:inline-block; vertical-align: top; margin:15px;cursor:pointer; " @click="toggle">
        {{title}}
      </div>
      <div v-if="show" class="content">      
        <slot >default</slot>
      </div>      
    </div>
    
  </div>
</template>

<script>
export default {
  name: 'SectionPlain',
  props: ['title', 'color', 'size'],
  data() {
    return {
      show:false
    }
  },
  computed:{
    isLeft(){
      return this.direction == 'left';
    },
    isRight(){
      return !this.isLeft
    },
    style(){
      return {
        background: this.color,
        width:this.size+'px',
        height: this.size+'px'
      }
    }
  },
  methods:{
    toggle(){
      //this.$emit('toggle',this.title);
      this.show = !this.show;
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.section{
  text-align: left;
  display: block;
  margin: auto;
}
.wrapper{
  display: inline-block;
  font-size:.9em;
  
}


.banner{  
  cursor:pointer; 
  display:inline-block;
  box-shadow: 7px 7px 1px 1px black;
  border-radius: 25px;  
} 


.content{
  font-size: .8em;
  display:block;  
  padding: 10px 0 0 40px
}


</style>
