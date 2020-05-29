<template>
  <div class="home">
    <SearchLearn/>
    <AgenceStore :posi="true"/>
    <AgenceStore :posi="false"/>
    <v-row>
      <AgenceStore :posi="false"/>
      <AgenceStore :posi="false"/>
      <AgenceStore :posi="false"/>
      <AgenceStore :posi="false"/>
      <AgenceStore :posi="false"/>    
    </v-row>
  </div>
</template>

<script>
// @ is an alias to /src
import AgenceStore from '../components/agence_stores/AgenceStore.vue'
import SearchLearn from '../components/learn_bike/Search.vue'

export default {
  name: 'Home',
  components: {
    AgenceStore,
    SearchLearn
  }
}
</script>
