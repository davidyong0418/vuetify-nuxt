<template>
  <v-card>
    <v-toolbar
      light>
      <v-toolbar-side-icon />

      <v-toolbar-title class="font14">Sort by <span style="color: cornflowerblue">{{ sort }}</span></v-toolbar-title>
      <v-menu
        bottom
        left
      >
        <v-btn
          slot="activator"
          icon>
          <v-icon style="font-size: 18px;">arrow_drop_down</v-icon>
        </v-btn>
        <v-list class="view-sort-menu">
          <v-list-tile>
            <v-list-tile-action @click="sort='test1'">Date</v-list-tile-action>
          </v-list-tile>
          <v-list-tile>
            <v-list-tile-action @click="sort='test2'">Highlights</v-list-tile-action>
          </v-list-tile>
          <v-list-tile>
            <v-list-tile-action @click="sort='test3'">Goals</v-list-tile-action>
          </v-list-tile>
          <v-divider />

          <v-list-tile>
            <v-list-tile-content class="subheader">Category</v-list-tile-content>
          </v-list-tile>

          <v-list-tile>
            <v-list-tile-action @click="sort='test4'">Arts</v-list-tile-action>
          </v-list-tile>
          <v-list-tile>
            <v-list-tile-action @click="sort='test1'">Awards</v-list-tile-action>
          </v-list-tile>
          <v-list-tile>
            <v-list-tile-action @click="sort='test2'">Birthdays</v-list-tile-action>
          </v-list-tile>
          <v-list-tile>
            <v-list-tile-action @click="sort='test3'">Familly</v-list-tile-action>
          </v-list-tile>
          <v-list-tile>
            <v-list-tile-action @click="sort='test4'">Field Trips</v-list-tile-action>
          </v-list-tile>
          <v-list-tile>
            <v-list-tile-action @click="sort='test1'">Food</v-list-tile-action>
          </v-list-tile>
          <v-list-tile>
            <v-list-tile-action @click="sort='test2'">Games</v-list-tile-action>
          </v-list-tile>
          <v-list-tile>
            <v-list-tile-action @click="sort='test3'">Movies</v-list-tile-action>
          </v-list-tile>
          <v-list-tile>
            <v-list-tile-action @click="sort='test4'">Music</v-list-tile-action>
          </v-list-tile>

          <v-list-tile>
            <v-list-tile-action @click="sort='test3'">School</v-list-tile-action>
          </v-list-tile>
          <v-list-tile>
            <v-list-tile-action @click="sort='test4'">Special Events</v-list-tile-action>
          </v-list-tile>
          <v-list-tile>
            <v-list-tile-action @click="sort='test1'">Sports</v-list-tile-action>
          </v-list-tile>
          <v-divider />

          <v-list-tile>
            <v-list-tile-content class="subheader">Metadata</v-list-tile-content>
          </v-list-tile>

        </v-list>
      </v-menu>

    </v-toolbar>

    <v-list>
      <template v-for="(item, index) in items">
        <v-subheader
          v-if="item.header"
          :key="index"
          class="deep-purple--text"
        >
          {{ item.header }}
        </v-subheader>

        <v-list-tile
          v-else
          :key="index"
          :class="{ activepeople : active_el == index }"
          avatar
          @click="activate(index)"
        >
          <v-list-tile-avatar>
            <img :src="item.avatar">
          </v-list-tile-avatar>

          <v-list-tile-content>
            <v-list-tile-title v-html="item.title" />
            <v-list-tile-sub-title v-html="item.subtitle" />
          </v-list-tile-content>
        </v-list-tile>
        <v-divider
          :key="index+20"
          class="mt-1 mb-1"/>
      </template>
    </v-list>
  </v-card>
</template>
<style>
.v-subheader {
  height: 100%;
}
.activepeople .v-list__tile {
  background: white;
  padding: 0;
  margin-left: 10px;
  padding-left: 10px;
}
.activepeople {
  background-color: orange;
}
</style>
<script>
export default {
  props: {
    propsmini: {
      type: Boolean,
      default: true
    }
  },
  data() {
    return {
      mini: this.propsmini,
      activeIndex: '',
      active_el: 0,
      sort: 'teste',
      items: [
        { header: 'Davis Home' },
        {
          avatar: 'https://cdn.vuetifyjs.com/images/lists/1.jpg',
          title: 'Brunch this weekend?',
          subtitle: '05/12/2018'
        },
        {
          avatar: 'https://cdn.vuetifyjs.com/images/lists/2.jpg',
          title: 'Summer BBQ',
          subtitle: '06/12/2018'
        },
        {
          avatar: 'https://cdn.vuetifyjs.com/images/lists/3.jpg',
          title: 'Oui oui',
          subtitle: '07/12/2018'
        },
        { header: 'Emerson Home' },
        {
          avatar: 'https://cdn.vuetifyjs.com/images/lists/4.jpg',
          title: 'Brunch this weekend?',
          subtitle: '05/12/2018'
        },
        {
          avatar: 'https://cdn.vuetifyjs.com/images/lists/2.jpg',
          title: 'Summer BBQ',
          subtitle: '06/12/2018'
        },
        {
          avatar: 'https://cdn.vuetifyjs.com/images/lists/3.jpg',
          title: 'Oui oui',
          subtitle: '07/12/2018'
        },
        { header: 'Garcia Home' },
        {
          avatar: 'https://cdn.vuetifyjs.com/images/lists/5.jpg',
          title: 'Brunch this weekend?',
          subtitle: '05/12/2018'
        },
        {
          avatar: 'https://cdn.vuetifyjs.com/images/lists/2.jpg',
          title: 'Summer BBQ',
          subtitle: '06/12/2018'
        },
        {
          avatar: 'https://cdn.vuetifyjs.com/images/lists/4.jpg',
          title: 'Oui oui',
          subtitle: '07/12/2018'
        },
        { header: 'Henley Home' },
        {
          avatar: 'https://cdn.vuetifyjs.com/images/lists/5.jpg',
          title: 'Brunch this weekend?',
          subtitle: '05/12/2018'
        },
        {
          avatar: 'https://cdn.vuetifyjs.com/images/lists/2.jpg',
          title: 'Summer BBQ',
          subtitle: '06/12/2018'
        },
        {
          avatar: 'https://cdn.vuetifyjs.com/images/lists/3.jpg',
          title: 'Oui oui',
          subtitle: '07/12/2018'
        }
      ]
    }
  },
  watch: {
    propsmini(newVal, oldVal) {
      this.mini = this.propsmini
    }
  },
  methods: {
    activate(el) {
      this.active_el = el
    },
    increment() {
      this.$store.commit('increment')
    }
  }
}
</script>
