<template>
  <div 
    id="main"> 
    <sidebar />
    <div 
      id="app"
      class="container-fluid">
      <div class="row">
        <div class="col col-2">
          Drawer
        </div>
        <div 
          id="timeline"
          class="col container">
          <keep-alive>
            <component :is="currentTimelineComponent" />
          </keep-alive>        
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Logo from '~/components/Logo.vue'
import Sidebar from '~/components/Sidebar.vue'
import PostToTimeline from '~/components/timeline/PostToTimeline.vue'
import ViewTimeline from '~/components/timeline/ViewTimeline.vue'

export default {
  components: {
    Logo,
    Sidebar,
    PostToTimeline,
    ViewTimeline
  },
  data: function() {
    return {
      currentTimelineComponent: ViewTimeline
    }
  }
}
</script>

<style>
#app {
  margin-left: 200px;
}

#main {
  min-height: 100vh;
  margin: 0;
  padding: 0;
}

#timeline {
  padding-top: 2rem;
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
