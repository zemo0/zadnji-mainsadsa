<template>
<div>
  <br><br><br><br><br>
<div id='container'>
    <ejs-schedule :height='height' :selectedDate='selectedDate' :views = 'views' :eventSettings='eventSettings'></ejs-schedule>
</div>
</div>
</template>
<script>
import Vue from 'vue';
import {SchedulePlugin, Day, Agenda } from '@syncfusion/ej2-vue-schedule';

let data = [{
Id: 1,
Subject: 'Sastanak',
StartTime: new Date(2018, 1, 15, 10, 0),
EndTime: new Date(2018, 1, 15, 12, 30)
}];

Vue.use(SchedulePlugin);
export default {
  data (){
return {
  height: '550px',
  views: ['Day', 'Agenda'],
  eventSettings: {
    dataSource: data
  },
  selectedDate: new Date(2018, 1, 15),
}
  },
  provide: {
schedule: [Day, Agenda]
  }
}

</script>