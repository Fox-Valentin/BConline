<template>
  <div>
    <full-calendar class="test-fc" :events="fcEvents" 
      first-day='1' locale="zh_CN"
      @changeMonth="changeMonth"
      @eventClick="eventClick"
      @dayClick="dayClick"
      @moreClick="moreClick">
        <template slot="fc-header-right">
        </template>
        <template slot="fc-event-card" scope="p">
            <p>{{ p.event.title }}</p>
        </template>
        <template slot="body-card-form">
          <li>
            <label for="">供应商结算价</label>
            <input type="text" readonly class="readonlyIpt">
          </li>
          <li>
            <label for="">默认分销价</label>
            <input type="text">
          </li>
          <li>
            <label for="">共享库存</label>
            <input type="text">
          </li>
          <button>提交</button>
        </template>
    </full-calendar>
  </div>
</template>
<script>
let demoEvents = [
  {
    title: 'Sunny 2/25-2/27',
    start: '2017-02-25',
    end: '2017-02-27',
    cssClass: 'family'
  },
  {
    title: 'Lunfel 726-727',
    start: '2017-02-26',
    end: '2017-02-27',
    cssClass: ['home', 'work']
  },
  {
    title: 'Lunfel 2/27-2/28',
    start: '2017-02-27',
    end: '2017-02-28'
  },
  {
    title: 'Lunfel 2/27-2/28',
    start: '2017-02-27',
    end: '2017-02-28'
  },
  {
    title: 'Lunfel 2/27-2/28',
    start: '2017-02-27',
    end: '2017-02-28'
  },
  {
    title: 'Lunfel 2/26-3/05',
    start: '2017-02-26',
    end: '2017-03-05'
  },
  {
    title: 'Lunfel 1/27-1/28',
    start: '2017-01-27',
    end: '2017-01-28'
  },
  {
    title: 'Lunfel 1/27-2/2',
    start: '2017-01-27',
    end: '2017-02-02'
  },
  {
    title: 'Lunfel 3/27-3/28',
    start: '2017-03-27',
    end: '2017-03-28'
  },
  {
    title: 'Lunfel 2/27-2/28',
    start: '2017-07-01',
    end: '2017-07-28',
    settlement: 22,
    distribution: 22,
    inventoryPooling: 20
  }
]

export default {
  data () {
    return {
      name: 'Sunny!',
      fcEvents: demoEvents
    }
  },
  methods: {
    'changeMonth' (start, end, current) {
      console.log('changeMonth', start.format(), end.format(), current.format())
    },
    'eventClick' (event, jsEvent, pos) {
      console.log('eventClick', event, jsEvent, pos)
    },
    'dayClick' (day, jsEvent) {
      console.log('dayClick', day, jsEvent)
    },
    'moreClick' (day, events, jsEvent) {
      console.log('moreCLick', day, events, jsEvent)
    }
  },
  components: {
    'full-calendar': require('../calendar/fullCalendar')
  }
}
</script>
<style lang='scss'>
  .app{
    color:green;
  }
  .family{
    color:red;
  }
</style>
