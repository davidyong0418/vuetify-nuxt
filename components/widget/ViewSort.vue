<template>
  <v-menu
    class="ml-5"
    bottom
    left
  >
    <v-btn
      slot="activator"
      icon>
      View by {{ sort }}
      <v-icon style="font-size: 18px;">arrow_drop_down</v-icon>
    </v-btn>
    <v-list class="view-sort-menu">
      <v-list-tile>
        <v-list-tile-action @click="sort='Date'">Date</v-list-tile-action>
      </v-list-tile>
      <v-list-tile>
        <v-list-tile-action @click="sort='Highlights'">Highlights</v-list-tile-action>
      </v-list-tile>
      <v-list-tile>
        <v-list-tile-action @click="sort='Goals'">Goals</v-list-tile-action>
      </v-list-tile>
      <v-divider />

      <v-list-tile>
        <v-list-tile-content class="subheader">Category</v-list-tile-content>
      </v-list-tile>

      <v-list-tile>
        <v-list-tile-action @click="sort='Arts'">Arts</v-list-tile-action>
      </v-list-tile>
      <v-list-tile>
        <v-list-tile-action @click="sort='Awards'">Awards</v-list-tile-action>
      </v-list-tile>
      <v-list-tile>
        <v-list-tile-action @click="sort='Birthdays'">Birthdays</v-list-tile-action>
      </v-list-tile>
      <v-list-tile>
        <v-list-tile-action @click="sort='Familly'">Familly</v-list-tile-action>
      </v-list-tile>
      <v-list-tile>
        <v-list-tile-action @click="sort='Field Trips'">Field Trips</v-list-tile-action>
      </v-list-tile>
      <v-list-tile>
        <v-list-tile-action @click="sort='Food'">Food</v-list-tile-action>
      </v-list-tile>
      <v-list-tile>
        <v-list-tile-action @click="sort='Games'">Games</v-list-tile-action>
      </v-list-tile>
      <v-list-tile>
        <v-list-tile-action @click="sort='Movies'">Movies</v-list-tile-action>
      </v-list-tile>
      <v-list-tile>
        <v-list-tile-action @click="sort='Music'">Music</v-list-tile-action>
      </v-list-tile>

      <v-list-tile>
        <v-list-tile-action @click="sort='School'">School</v-list-tile-action>
      </v-list-tile>
      <v-list-tile>
        <v-list-tile-action @click="sort='Special Events'">Special Events</v-list-tile-action>
      </v-list-tile>
      <v-list-tile>
        <v-list-tile-action @click="sort='Sports'">Sports</v-list-tile-action>
      </v-list-tile>
      <v-divider />

      <v-list-tile>
        <v-list-tile-content class="subheader">Metadata</v-list-tile-content>
      </v-list-tile>

    </v-list>
  </v-menu>
</template>
<style>
.view-sort-menu .v-list__tile {
  min-width: 200px;
}
.view-sort-menu .v-divider {
  margin-bottom: 5px !important;
  margin-top: 5px !important;
}
.view-sort-menu .subheader {
  color: grey;
}
.view-sort-menu .v-list__tile {
  height: 40px;
}
</style>
<script>
export default {
  data() {
    return {
      sort: 'Date'
    }
  }
}
</script>
