<template>
  <div class="home">
    
    You need {{need}} (character traits)


    <br />
    Service matters.

    <ul>      
      <li>Tranparency - know status and progress while enjoying less human management.</li>
      <li>Communication - expect Honesty, Clarity, Responsiveness, </li>
      <li>Relationships - we are people people, not just computer people.</li>
    </ul>
    
  Skills


  </div>
</template>

<script>
// @ is an alias to /src

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
  }
}
</script>
