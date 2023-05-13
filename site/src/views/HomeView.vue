<template>
  <div class="home">
    
    You need {{need}}


    <br />
    Service matters.

    <ul>      
      <li>Tranparency - know status and progress while enjoying less human management.</li>
      <li>Communication - expect Honesty, Clarity, Responsiveness, </li>
      <li>Relationships - we are people people, not just computer people.</li>
    </ul>
    
  Skills

  <Section :direction="'left'">
    <H1>Web applications</H1>
  </Section>

  <Section :direction="'right'">
    <H1>3D Modeling</H1>
  </Section>

  <Section :direction="'left'">
    <H1>Drone Videography</H1>
  </Section>

  </div>
</template>

<script>
// @ is an alias to /src
import Section from '@/components/Section.vue';
export default {
  name: 'HomeView',
  computed:{
    
  },
  data: function () {
    return {
      need: "", 
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
    changeNeed: function(){
      setTimeout(() => {
        this.needTimeout();
        this.changeNeed();
      }, 1000)

    },
    needTimeout: function(){
      let i = Math.random()*this.needs.length;      
      i = Math.round(i);
      console.log(i);
      this.need = this.needs[i];
      
    }
  },
  components: {
    Section
  }
}
</script>
