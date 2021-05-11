<template>
<div class="container mx-auto">
  <h2 class="text-center">To Send</h2>
  <AddToSend @addClimbEvent="addClimbToSend"/>
  <ul class="divide-y divide-gray-200">
    <li v-for="(climb, index) in climbs" :key="index" class="py-4 flex">
      <ClimbCard :climb="climb"/>
    </li>
  </ul>
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
      climbs: [
        {
        name: 'Apollon',
        grade: '5.11',
        style: 'trad',
        sent: false,
      },
        {
        name: 'Orgasmotron',
        grade: '5.12',
        style: 'sport',
        sent: false,
      },
        {
        name: 'Moby Dick',
        grade: '5.11',
        style: 'sport',
        sent: false,
      },
      ],
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
