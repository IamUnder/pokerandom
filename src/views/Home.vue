<template>
  <div class="bg-yellow-300 items-center h-screen">
    <div class="text-4xl">
      Hello 👋🏼
      <options></options>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
//import HelloWorld from '@/components/HelloWorld.vue'
import Options from '@/components/Options.vue'

export default {
  name: 'Home',
  components: {
    Options
  }
}
</script>
