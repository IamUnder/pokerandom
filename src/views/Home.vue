<template>
  <div class="justify-center  bg-yellow-300 items-center h-screen">
    <options @getData="getData" ></options>
    <div>
      <table class="table-auto">
        <thead>
          <tr>
            <th>ID</th>
            <th>Name</th>
            <th>Nº Moves</th>
            <th>Sprite</th>
            <th>evo</th>
            <th>Preevo</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="pok in generate" v-bind:key="pok">
            <td>{{pok.id}}</td>
            <td>{{pok.name}}</td>
            <td>{{pok.moves}}</td>
            <td>
              <img :src="pok.sprite" alt="" srcset="">
            </td>
            <td>{{pok.evo}}</td>
            <td>{{pok.preevo}}</td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
//import HelloWorld from '@/components/HelloWorld.vue'
import Options from '@/components/Options.vue'

export default {
  name: 'Home',
  data () {
    return {
      generate: []
    }
  },
  methods: {
    getData(data) {
      this.generate = data
    }
  }, 
  components: {
    Options
  }
}
</script>
