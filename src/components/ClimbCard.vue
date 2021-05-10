<template>
<p>
  {{ climb.name }}
  {{ climb.grade }}
  {{ climb.style }}
</p>
</template>

<script>
export default {
  name: 'ClimbCard',
  props: ['climb']
  
}
</script>