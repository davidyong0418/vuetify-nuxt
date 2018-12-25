<template>
  <v-layout>
    <v-flex
      v-if="propsmini"
      sm4
      class="scrol-operation"
    >
      <people-list />
    </v-flex>
    <v-flex
      v-if="propsmini==true"
      sm8
      class="scrol-operation"
    >
      <over-view
        :propsmini.sync="propsmini" />
    </v-flex>
    <v-flex
      v-if="propsmini==false"
      sm12
      class="scrol-operation"
    >
      <over-view
        :propsmini.sync="propsmini" />
    </v-flex>
  </v-layout>
</template>
<style>
.scrol-operation {
  max-height: 100vh;
  overflow-y: scroll;
}
</style>
<script>
import PeopleList from '../components/PeopleList'
import OverView from '../components/OverView'
export default {
  components: {
    PeopleList,
    OverView
  },
  props: {
    source: {
      type: String,
      default: ''
    }
  },
  data() {
    return {
      propsmini: true,
      drawer: null,
      peopledata: {}
    }
  }
}
</script>
