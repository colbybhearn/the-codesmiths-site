<template>
  <div class="home">
    
    <br />
    Do you need <u>{{need}}</u>?    <br/>
    Forge ahead with <b><i>The Codesmiths</i></b>
    <br />
    <br />
    
  

  <SectionPlain :title="'what we do'" :color="'red'" :size="100" @toggle="toggle">
    
    <SectionPlain :title="'Web applications'" :color="'red'" :size="50" >
      <div class="list">
        <ul style="text-align:left;">      
          <li>Online product configurators</li>
          <li>Internal tools for your team</li>
          <li>Integration with 3rd parties</li>          
        </ul>
      </div>
      </SectionPlain>
      <SectionPlain :title="'3D modeling and visualizations'" :color="'red'" :size="50" >
        <div class="list">
          <ul style="text-align:left;">      
            <li>3D Design Tools</li>
            <li>Product Visualization</li>
            <li>Unique Interactive graphics</li>          
          </ul>
      </div>
    </SectionPlain>
    <SectionPlain :title="'Drone Videography'" :color="'red'" :size="50" >
        <div class="list">
          <ul style="text-align:left;">      
            <li></li>
            <li>Database Design</li>
            <li>Requirements Analysis</li>          
          </ul>
      </div>
    </SectionPlain>

  </SectionPlain>

  <SectionPlain :title="'how we work'" :color="'green'" :size="100" @toggle="toggle">
    <SectionPlain :title="'Service matters... a lot.'" :color="'green'" :size="50" >
      
  <div >
      <ul style="text-align:left;">      
        <li>Tranparency - know status and progress while enjoying less human management.</li>
        <li>Communication - expect honesty, clarity, responsiveness, </li>
        <li>Relationships - we are people people, not just computer people.</li>
        <li>Accountability - everyone is accountable to Someone, and that's good.</li>
      </ul>
    </div>
    </SectionPlain>
    <SectionPlain :color="'green'" :size="50" >more</SectionPlain>
  </SectionPlain>

  <SectionPlain :title="'more about us'" :color="'blue'" :size="100" @toggle="toggle">
    <SectionPlain :color="'blue'" :size="50" >more</SectionPlain>
    <SectionPlain :color="'blue'" :size="50" >more</SectionPlain>
  </SectionPlain>

  </div>
</template>

<script>
// @ is an alias to /src
import SectionPlain from '@/components/SectionPlain.vue'
export default {
  name: 'HomeView',
  computed:{
    
  },
  data: function () {
    return {
      need: "help", 
      needs: [
        "thinkers",
        "doers",
        "self-starters",
        "coders",
        "transparency",
        "communication",
        "relationships",
        "integrators",
        "smart-workers",
      ]
    }
  },
  
  mounted: function(){
    this.changeNeed();
  },
  methods:{
    toggle: function(name){
      console.log(name);
    },
    changeNeed: function(){
      setTimeout(() => {
        this.needTimeout();
        this.changeNeed();
      }, 5000)

    },
    needTimeout: function(){
      let i = Math.random()*this.needs.length;      
      i = Math.round(i);
      //console.log(i);
      this.need = this.needs[i];
      
    }
  },
  components: {
    SectionPlain
  }
}
</script>

<style scoped>
.home{
  font-size: 2em;
  text-align: center;
  margin: auto;
  display: inline-block;
}
</style>