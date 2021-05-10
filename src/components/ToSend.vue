<template>
<div>
  <h2>To Send</h2>
  <AddToSend @addClimbEvent="addClimbToSend"/>
  <ClimbCard v-for="climb in climbs" :key="climb.name" :climb="climb"/>
</div>
</template>

<script>
import AddToSend from './AddToSend';
import ClimbCard from './ClimbCard';

export default {
  name: 'ToSend',
  components: {
    AddToSend,
    ClimbCard
  },
  data: function() {
    return {
      climbs: [{
        name: 'Apollon',
        grade: '5.11',
        style: 'trad',
        sent: false,
      }],
    }
  },
  methods: {
    addClimbToSend(climb) {
      console.log({climb})
      this.climbs = [...this.climbs, climb];
    }
  }
}
</script>
