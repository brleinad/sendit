<template>
<div class="ml-3">
  <p class="text-sm font-medium text-gray-900">{{ climb.name }}</p>
  <p class="text-sm text-gray-500">{{ climb.grade }}</p>
</div>
</template>

<script>
export default {
  name: 'ClimbCard',
  props: ['climb']
  
}
</script>