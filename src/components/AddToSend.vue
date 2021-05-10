<template>
<div>
  <!-- <label></label> -->
  <input type="text" v-model="climb.name"/>
  <input type="text" v-model="climb.grade"/>
  <button @click="addClimb">Add</button>
</div>
</template>

<script>
// TODO: validator for grade or just dropdown
// TODO: validator for name: required and non empty
export default {
  name: 'AddToSend',
  data: function() {
    return {
      climb: {
        name: '',
        grade: '',
        style: '',
        sent: false}
      }
    },
    methods: {
      addClimb() {
        this.$emit('addClimbEvent', {
          name: this.climb.name,
          grade: this.climb.grade,
          style: this.climb.style,
          sent: this.climb.sent,
        });
        this.clearClimb();
      },
      clearClimb() {
        this.climb = { 
          name: '',
          grade: '',
          style: '',
          sent: false,
        }
      }
    },
    emits: ['addClimbEvent']
}
</script>