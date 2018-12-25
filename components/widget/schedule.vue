<template>
  <div>
    <div class="schedule">
      <div class="schedule-date pr-4 pl-4 pt-3">
        <v-divider />
        <span class="ml-2 mr-2">07/29/2018</span>
        <v-divider />
      </div>
      <div class="schedule-title text-center font18 pt-4 pb-4">
        Cody turned 9
      </div>
      <div class="schedule-highlight pl-5 pr-5 pb-4">
        <div class="pl-5 pr-5 schedule-highlight-child">
          <v-divider />
          <v-icon
            class="font16 ml-2"
            color="red">calendar_today</v-icon>
          <span class="font16 margin-auto mr-2">Highlight</span>
          <v-divider />
        </div>
      </div>
    </div>
  </div>
</template>
<style>
.font18 {
  font-size: 24px;
}
.schedule {
  border-radius: 15px;
  border: 1px solid grey;
}
.schedule-date {
  display: flex;
}
.schedule-date span {
  margin: auto;
}
.schedule-highlight-child {
  display: flex;
}
</style>
