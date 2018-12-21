<template>
  <div 
    id="timeline"
    class="container">
    <b-button
      @click="showCreateTimelinePost">
      Add Post</b-button>
  </div>
</template>

<style>
#timeline {
  padding-top: 2rem;
}
</style>

<script>
import PostToTimeline from '~/components/timeline/PostToTimeline.vue'

export default {
  components: {
    PostToTimeline
  },

  methods: {
    showCreateTimelinePost() {
      this.currentTimelineComponent = PostToTimeline
      alert('Hello')
    }
  }
}
</script>
