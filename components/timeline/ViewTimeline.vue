<template>
  <v-container class="viewtimeline">
    <v-list class="pa-0">
      <v-list-tile avatar>
        <v-list-tile-avatar>
          <img src="https://randomuser.me/api/portraits/men/85.jpg">
        </v-list-tile-avatar>
        <v-list-tile-content>
          <v-list-tile-title>John Leider</v-list-tile-title>
        </v-list-tile-content>

        <v-btn
          v-if="post==false"
          absolute
          dark
          fab
          bottom
          right
          color="cyan"
          @click="newpost"
        >
          <v-icon>add</v-icon>
        </v-btn>
      </v-list-tile>
      <v-divider class="overview-header"/>

    </v-list>
    <div
      v-if="post==false">
      <view-sort />
    </div>
    <v-card v-if="post==false">
      <v-flex>
        <v-card-title primary-title>
          <v-flex sm12>
            <div class="stepper-date">
              <span class="stepper-date-letter">06/04/2018</span>
              <v-divider />
              <v-icon color="deep-purple lighten-1">local_car_wash</v-icon>
              <span class="stepper-date-letter">Family</span>
            </div>
          </v-flex>
          <v-flex
            sm12
            md12>
            <h5 class="mb-0 deep-purple--text">Kangaroo Valley Safari</h5>
            <div
              class="display-flex overview-explain"
              row
              flex>
              <div
                class="font12 explain-text"
                sm8>Located two hours south of Sydney in the Southern Highlands of New South Wales, ...
              </div>
              <div
                class="explain-edit"
                sm4>
                <v-icon
                  small
                  bottom
                  absolute>edit</v-icon>

              </div>
            </div>
          </v-flex>
        </v-card-title>
        <v-card-title>
          <v-img
            src="https://cdn.vuetifyjs.com/images/cards/desert.jpg"
            aspect-ratio="1.65"
          />
        </v-card-title>

        <v-spacer />
      </v-flex>
      <v-flex>
        <v-card-title primary-title>
          <v-flex sm12>
            <div class="stepper-date">
              <span class="stepper-date-letter">06/04/2018</span>
              <v-divider />
              <v-icon color="deep-purple lighten-1">local_car_wash</v-icon>
              <span class="stepper-date-letter">Family</span>
            </div>
          </v-flex>
          <v-flex
            sm12
            md12>
            <h5 class="mb-0 deep-purple--text">Kangaroo Valley Safari</h5>
            <div
              class="display-flex overview-explain"
              row
              flex>
              <div
                class="font12 explain-text"
                sm8>Located two hours south of Sydney in the Southern Highlands of New South Wales, ...
              </div>
              <div
                class="explain-edit"
                sm4>
                <v-icon
                  small
                  bottom
                  absolute>edit</v-icon>

              </div>
            </div>
          </v-flex>
        </v-card-title>
        <v-card-title>
          <v-img
            src="https://cdn.vuetifyjs.com/images/cards/desert.jpg"
            aspect-ratio="1.65"
          />
        </v-card-title>

        <v-spacer />
      </v-flex>
    </v-card>
    <v-card v-if="post==true">
      <v-stepper
        v-model="e6"
        vertical>
        <v-stepper-step
          :complete="e6 > 1"
          step="1">
          New Post
        </v-stepper-step>

        <v-stepper-content step="1">

          <label class="custom-lc">Photo</label>
          <dropzone
            id="foo"
            ref="el"
            :options="dropOptions"/>
          <label class="custom-lc">Date</label>
          <v-menu
            ref="menu1"
            :close-on-content-click="false"
            v-model="menu1"
            :nudge-right="40"
            lazy
            transition="scale-transition"
            offset-y
            full-width
            max-width="290px"
            min-width="290px"
          >
            <v-text-field
              slot="activator"
              v-model="dateFormatted"
              hint="MM/DD/YYYY format"
              persistent-hint
              prepend-icon="event"
              outline
              @blur="date = parseDate(dateFormatted)" />
            <v-date-picker
              v-model="date"
              no-title
              @input="menu1 = false" />
          </v-menu>
          <label class="custom-lc">Title</label>
          <v-text-field
            v-model="title"
            outline
            required />
          <label class="custom-lc">Description</label>
          <v-text-field
            v-model="description"
            outline
            required />
          <label class="custom-lc">Select Category</label>
          <v-select
            :items="items"
            outline />
          <div style="float: right">
            <v-btn
              outline
              color="info"
              @click="post=false"
            >Cancel</v-btn>
            <v-btn
              color="info"
              @click="post=false">Post</v-btn>
          </div>


        </v-stepper-content>

      </v-stepper>
    </v-card>
  </v-container>
</template>
<style>
.viewtimeline input {
  margin: auto;
}
</style>
<script>
import Dropzone from 'nuxt-dropzone'
import 'nuxt-dropzone/dropzone.css'
import ViewSort from '../widget/ViewSort'
export default {
  components: {
    Dropzone,
    ViewSort
  },
  data: vm => ({
    tab: null,
    items: ['web', 'shopping', 'videos', 'images', 'news'],
    post: false,
    title: '',
    description: '',
    dateFormatted: vm.formatDate(new Date().toISOString().substr(0, 10)),
    date: new Date().toISOString().substr(0, 10),
    menu1: false,
    computedDateFormattedMomentjs: '',
    e6: 1,
    options: {
      url: 'http://guru.org/'
    },
    dropOptions: {
      url: 'https://httpbin.org/post',
      maxFilesize: 2, // MB
      maxFiles: 4,
      chunking: true,
      chunkSize: 500, // Bytes
      thumbnailWidth: 150, // px
      thumbnailHeight: 150,
      addRemoveLinks: true,
      dictDefaultMessage:
        '<p class="dropzone-span">Drag and drop your files</p>' +
        'anywhere or browse'
    }
  }),
  computed: {
    computedDateFormatted() {
      return this.formatDate(this.date)
    }
  },
  watch: {
    date(val) {
      this.dateFormatted = this.formatDate(this.date)
    }
  },
  methods: {
    newpost() {
      this.post = true
    },
    formatDate(date) {
      if (!date) return null

      const [year, month, day] = date.split('-')
      return `${month}/${day}/${year}`
    },
    parseDate(date) {
      if (!date) return null
      const [month, day, year] = date.split('/')
      return `${year}-${month.padStart(2, '0')}-${day.padStart(2, '0')}`
    }
  }
}
</script>
