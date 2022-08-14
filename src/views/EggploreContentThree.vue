<template>
  <div class="search-container">
    <div class="search-content">
      <div class="search-bar">
        <h5>Search Bar</h5>
        <div class="search-bar-content">
          <input
            type="text"
            class="search-input"
            placeholder="Enter a city or landmark..."
            v-model="search_input"
          />
          <svg
            width="20"
            height="20"
            viewBox="0 0 20 20"
            fill="currentcolor"
            xmlns="http://www.w3.org/2000/svg"
            :class="search_input ? 'search-svg-active' : 'search-svg-deactive'"
          >
            <path
              d="M19.0536 18.046C19.3319 18.3242 19.3319 18.7754 19.0536 19.0536C18.7754 19.3319 18.3242 19.3319 18.046 19.0536L14.626 15.6336C14.3477 15.3554 14.3477 14.9042 14.626 14.626C14.9042 14.3477 15.3554 14.3477 15.6336 14.626L19.0536 18.046ZM8.2898 15.8423C4.11867 15.8423 0.737305 12.4609 0.737305 8.2898C0.737305 4.11867 4.11867 0.737305 8.2898 0.737305C12.4609 0.737305 15.8423 4.11867 15.8423 8.2898C15.8423 12.4609 12.4609 15.8423 8.2898 15.8423ZM8.2898 14.4173C11.6739 14.4173 14.4173 11.6739 14.4173 8.2898C14.4173 4.90568 11.6739 2.1623 8.2898 2.1623C4.90568 2.1623 2.1623 4.90568 2.1623 8.2898C2.1623 11.6739 4.90568 14.4173 8.2898 14.4173ZM4.7748 7.7198C4.7748 7.98214 4.56214 8.1948 4.2998 8.1948C4.03747 8.1948 3.8248 7.98214 3.8248 7.7198C3.8248 5.56866 5.56866 3.8248 7.7198 3.8248C7.98214 3.8248 8.1948 4.03747 8.1948 4.2998C8.1948 4.56214 7.98214 4.7748 7.7198 4.7748C6.09333 4.7748 4.7748 6.09333 4.7748 7.7198Z"
              fill="currentcolor"
            />
          </svg>

          <svg
            width="12"
            height="12"
            viewBox="0 0 12 12"
            fill="currentcolor"
            xmlns="http://www.w3.org/2000/svg"
            :class="
              search_input ? 'delete-search-active' : 'delete-search-deactive'
            "
            @click="deleteSearchInput"
          >
            <path
              d="M6 0C2.7 0 0 2.7 0 6C0 9.3 2.7 12 6 12C9.3 12 12 9.3 12 6C12 2.7 9.3 0 6 0ZM8.625 7.575L7.575 8.625L6 7.05L4.425 8.625L3.375 7.575L4.95 6L3.375 4.425L4.425 3.375L6 4.95L7.575 3.375L8.625 4.425L7.05 6L8.625 7.575Z"
              fill="currentcolor"
            />
          </svg>
        </div>

        <div class="search-one-bar">
          <input
            type="text"
            class="search-input-one"
            @keyup="findRegion"
            v-model="input_one_found"
            placeholder="Enter a city or landmark..."
          />
          <svg
            width="20"
            height="20"
            viewBox="0 0 20 20"
            fill="currentcolor"
            xmlns="http://www.w3.org/2000/svg"
            :class="
              input_one_found ? 'one-active-search' : 'one-deactive-search'
            "
          >
            <path
              d="M19.0536 18.046C19.3319 18.3242 19.3319 18.7754 19.0536 19.0536C18.7754 19.3319 18.3242 19.3319 18.046 19.0536L14.626 15.6336C14.3477 15.3554 14.3477 14.9042 14.626 14.626C14.9042 14.3477 15.3554 14.3477 15.6336 14.626L19.0536 18.046ZM8.2898 15.8423C4.11867 15.8423 0.737305 12.4609 0.737305 8.2898C0.737305 4.11867 4.11867 0.737305 8.2898 0.737305C12.4609 0.737305 15.8423 4.11867 15.8423 8.2898C15.8423 12.4609 12.4609 15.8423 8.2898 15.8423ZM8.2898 14.4173C11.6739 14.4173 14.4173 11.6739 14.4173 8.2898C14.4173 4.90568 11.6739 2.1623 8.2898 2.1623C4.90568 2.1623 2.1623 4.90568 2.1623 8.2898C2.1623 11.6739 4.90568 14.4173 8.2898 14.4173ZM4.7748 7.7198C4.7748 7.98214 4.56214 8.1948 4.2998 8.1948C4.03747 8.1948 3.8248 7.98214 3.8248 7.7198C3.8248 5.56866 5.56866 3.8248 7.7198 3.8248C7.98214 3.8248 8.1948 4.03747 8.1948 4.2998C8.1948 4.56214 7.98214 4.7748 7.7198 4.7748C6.09333 4.7748 4.7748 6.09333 4.7748 7.7198Z"
              fill="currentcolor"
            />
          </svg>

          <svg
            width="12"
            height="12"
            viewBox="0 0 12 12"
            fill="currentcolor"
            xmlns="http://www.w3.org/2000/svg"
            :class="
              input_one_found ? 'one-active-delete' : 'one-deactive-delete'
            "
            @click="deleteSearchInputOne"
          >
            <path
              d="M6 0C2.7 0 0 2.7 0 6C0 9.3 2.7 12 6 12C9.3 12 12 9.3 12 6C12 2.7 9.3 0 6 0ZM8.625 7.575L7.575 8.625L6 7.05L4.425 8.625L3.375 7.575L4.95 6L3.375 4.425L4.425 3.375L6 4.95L7.575 3.375L8.625 4.425L7.05 6L8.625 7.575Z"
              fill="currentcolor"
            />
          </svg>
          <div
            :class="input_one_found ? 'wrap-one-active' : 'wrap-one-deactive'"
            v-for="(found, idx) in region"
            :key="idx"
          >
            <span>{{ found }}</span>
          </div>
        </div>
      </div>
      <div class="direction-form">
        <eggplore-location/>
      </div>
      <div class="date-picker">
        <eggplore-calendar v-model="date" />
      </div>
      <div class="text-box"></div>
    </div>
  </div>
</template>
<script>
import EggploreLocation from './eggplore-three/EggploreLocation.vue'
import EggploreCalendar from './eggplore-three/EggploreCalendar.vue';
export default {
  name: "search-app",
  components:{EggploreLocation, EggploreCalendar},
  data() {
    return {
      
      own_destination: "Your location",
      search_input: null,
      input_one_found: null,
      region: [],
      date: new Date(),
      regions: [
        "Andijon",
        "Buxoro",
        "Farg'ona",
        "Jizzax",
        "Namangan",
        "Navoiy",
        "Samarqand",
        "Sirdaryo",
        "Surxondaryo",
        "Toshkent",
        "Qashqadaryo",
        "Xorazm",
      ],
    };
  },
  mounted() {},
  methods: {
    
    findRegion(e) {
      let input_value = e.target.value;
      this.region = this.regions.filter((item) => {
        item = item.toLowerCase();
        return item.includes(input_value.toLowerCase());
      });
      // this.regions.forEach((element) => {
      //   // let search_reg = element.toLowerCase
      //   let found_value = element.match(`${input_value}`);
      //   this.region = found_value;
      //   console.log(this.region);
      // });
      console.log(this.region);
    },
    
    deleteSearchInput() {
      this.search_input = null;
    },
    deleteSearchInputOne() {
      this.input_one_found = null;
    },
  },
  watch: {
    'date': function (val) {
      console.log(val)
    }
  }
};
</script>
<style>
.search-container .search-content .date-picker{
  width: 24%;
  margin-left: 20px;
}

</style>
