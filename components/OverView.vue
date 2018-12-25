<template>
  <div>
    <v-toolbar
      class="blue-grey darken-4"
      dark
      tabs>
      <v-toolbar-side-icon @click.stop="changeprops">
        <v-icon v-if="peoplemini==true">chevron_left</v-icon>
        <v-icon v-if="peoplemini==false">chevron_right</v-icon>
      </v-toolbar-side-icon>
      <v-spacer />
      <v-tabs
        v-model="tab"
        centered
        align-with-title
        color="transparent"
        hide-slider
        active-class="tab-activity"
        show-arrows
      >
        <v-tab
          key="1"
          href="#tab-1"
          class="font12 flex-column pl-3">
          Timeline
          <v-icon
            small
            class="mb-1">fa-bars</v-icon>
        </v-tab>

        <v-tab
          key="2"
          href="#tab-2"
          class="font12 flex-column pl-3">
          Pending
          <v-icon
            small
            class="mb-1">fa-desktop</v-icon>
        </v-tab>

        <v-tab
          href="#tab-3"
          class="font12 flex-column pl-3">
          Goal
          <v-icon
            small
            class="mb-1">fa-flag</v-icon>
        </v-tab>

        <v-tab
          href="#tab-4"
          class="font12 flex-column pl-3">
          Request
          <v-icon
            small
            class="mb-1">fa-location-arrow</v-icon>
        </v-tab>

        <v-tab
          href="#tab-5"
          class="font12 flex-column pl-3">
          Edit
          <v-icon
            small
            class="mb-1">edit</v-icon>
        </v-tab>
      </v-tabs>
      <v-spacer />
      <v-btn
        dark
        icon><v-icon>more_vert</v-icon></v-btn>
    </v-toolbar>
    <v-tabs-items v-model="tab">
      <v-tab-item
        id="tab-1"
        key="tab-1"
      >
        <view-timeline />
      </v-tab-item>
      <v-tab-item
        id="tab-2"
        key="tab-2"
      >
        <pending />
      </v-tab-item>
      <v-tab-item
        id="tab-3"
        key="tab-3"
      >
        <goal />
      </v-tab-item>
      <v-tab-item
        id="tab-4"
        key="tab-4"
      >
        <request />
      </v-tab-item>
      <v-tab-item
        id="tab-5"
        key="tab-5"
      >
        <edit />
      </v-tab-item>
    </v-tabs-items>
  </div>
</template>
<style>
.stepper-date-letter {
  margin: auto;
  font-size: 12px;
}
.stepper-date {
  display: flex;
  flex-direction: row;
}
.font10 {
  font-size: 10px;
}
.font12 {
  font-size: 12px;
}
.font14 {
  font-size: 14px;
}
.display-flex {
  display: flex;
}
.tab-activity .v-icon {
  color: orange;
}
.overview-explain .explain-text {
  width: 95%;
}
.vue-dropzone {
  border: 3px dotted #bdbdbd;
  border-radius: 5px;
  margin-bottom: 25px;
}
.dropzone-span {
  margin-bottom: 4px;
}
.dz-default.dz-message {
  font-size: 14px;
}
.custom-lc {
  color: #bdbdbd;
}
.v-menu .v-menu__activator .v-input__prepend-outer {
  position: absolute;
  margin-top: 16px;
  margin-left: 5px;
}
.v-menu .v-menu__activator .v-input__control .v-input__slot {
  padding-left: 25px;
}
.v-tabs__item:hover {
  color: orange;
  text-decoration: none;
}
.overview-header {
  margin: 0;
  margin-bottom: 10px;
}
.flex-column a {
  display: flex;
  flex-direction: column-reverse;
}
</style>

<script>
import ViewTimeline from './timeline/ViewTimeline'
import Pending from './pending/Pending'
import Goal from './goal/Goal'
import Request from './request/Request'
import Edit from './edit/Edit'
export default {
  components: {
    ViewTimeline,
    Pending,
    Goal,
    Request,
    Edit
  },
  props: {
    propsmini: {
      type: Boolean,
      default: true
    }
  },
  data: vm => ({
    peoplemini: vm.propsmini,
    tab: null,
    items: ['web', 'shopping', 'videos', 'images', 'news'],
    post: false,
    title: '',
    description: '',
    menu1: false,
    e6: 1,
    options: {
      url: 'http://guru.org/'
    }
  }),
  methods: {
    changeprops() {
      this.peoplemini = !this.peoplemini
      this.$emit('update:propsmini', this.peoplemini)
    }
  }
}
</script>
