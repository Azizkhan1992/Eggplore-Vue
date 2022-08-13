<template>
  <div class="calendar-container">
    <h5>Date Picker</h5>
    <div class="calendar-content">
      <div @click="calendarActive" class="calendar-visible">
        <svg
          width="16"
          height="16"
          viewBox="0 0 16 16"
          fill="currentcolor"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path
            d="M15 2C15.552 2 16 2.448 16 3V15C16 15.552 15.552 16 15 16H1C0.448 16 0 15.552 0 15V3C0 2.448 0.448 2 1 2H3V0H6V2H10V0H13V2H15ZM14 14V5H2V14H14ZM4 7H6V9H4V7ZM7 7H9V9H7V7Z"
            fill="currentcolor"
          />
        </svg>
      </div>
      <div class="calendar-hidden"></div>
    </div>
  </div>
</template>
<script>
export default {
  name: "eggplore-calendar",
  data(){
    return{
        isCalendarActive: false
    }
  },
  methods:{
    calendarActive(){
        this.isCalendarActive = ! this.isCalendarActive
    }
  }
};
</script>
<style>
.calendar-container {
  width: 100%;
  display: flex;
  flex-direction: column;
  padding: 5px 10px 5px 10px;
  box-sizing: border-box;
}
.calendar-container h5 {
  display: inline-block;
  margin: 0;
  font-size: 1rem;
  text-transform: uppercase;
  line-height: 24px;
}
.calendar-container .calendar-content {
  position: relative;
  width: 100%;
  display: flex;
  flex-direction: column;
  margin-top: 20px;
}
.calendar-container .calendar-content .calendar-visible {
  position: relative;
  width: 80%;
  height: 48px;
  background: #ffffff;
  border-radius: 5px;
  box-shadow: 0 7px 64px rgba(0, 0, 0, 0.07);
  cursor: pointer;
}
</style>
