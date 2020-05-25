<template>
  <div class="home">
    <SearchLearn/>
    <BikesStore :posi="true"/>
    <BikesStore :posi="false"/>
    <BikesStore :posi="false"/>
    <BikesStore :posi="false"/>
  </div>
</template>

<script>
// @ is an alias to /src
import BikesStore from '../components/agence_stores/AgenceStore.vue'
import SearchLearn from '../components/learn_bike/Search.vue'

export default {
  name: 'Home',
  components: {
    BikesStore,
    SearchLearn
  }
}
</script>
