<template>
<div class="flex flex-row">
  <div class="px-6">
    <label for="name" class="block text-sm font-medium text-gray-600">Climb Name</label>
    <div class="mt-1">
      <input required type="text" v-model="climb.name" placeholder="the nose" class=""/>
    </div>
  </div>

  <div class="">
    <label for="grade" class="block text-sm font-medium text-gray-600">Grade</label>
    <div class="mt-1">
      <input required type="text" v-model="climb.grade" placeholder="5.13"/>
    </div>
  </div>
  <button :disabled="isInvalidClimb" @click="addClimb" class="disabled:opacity-60 items-center px-2 py-1 border border-transparent text-xs rounded-xl font-medium shadow-sm text-white bg-blue-500 hover:bg-blue-300">Add</button>
</div>
</template>

<script>
// TODO: validator for grade or just dropdown
// TODO: validator for name: required and non empty
const emptyClimb = {
  name: '',
  grade: '',
  style: '',
  sent: false,
  };
export default {
  name: 'AddToSend',
  data: function() {
    return {
      climb: {
        name: '',
        grade: '',
        style: '',
        sent: false,
      },
    }
  },
  emits: ['addClimbEvent'],
  methods: {
    addClimb() {
      this.$emit('addClimbEvent', {...this.climb});
      this.clearClimb();
    },
    clearClimb() {
      this.climb = { ...emptyClimb };
    },
  },
  computed: {
    isInvalidClimb() {
      return this.climb.name === '' || this.climb.grade === '';
    }
  }
}
</script>