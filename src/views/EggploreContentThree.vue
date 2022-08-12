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
            v-for="(found, idx) in regions"
            :key="idx"
          >
            <span>{{ found }}</span>
          </div>
        </div>
      </div>
      <div class="direction-form">
        <h5>Direction Form</h5>
        <div class="direction-container">
          <div class="own-location"
          :class="isPathDirection ? 'own-location-active' : 'own-location-deactive'"
          >
            <div class="location-title">
              <svg
                width="16"
                height="16"
                viewBox="0 0 16 16"
                fill="currentcolor"
                xmlns="http://www.w3.org/2000/svg"
                class="own-location-svg"
              >
                <path
                  d="M0.768857 4.04917L14.596 0.098548C15.3861 -0.0989828 16.0775 0.592375 15.88 1.3825L11.9294 15.2097C11.6331 16.0985 10.4479 16.1973 10.0528 15.3084L7.28738 8.78991L0.768857 6.02447C-0.218798 5.53065 -0.120031 4.34546 0.768857 4.04917Z"
                  fill="currentcolor"
                />
              </svg>
              {{ own_destination }}
            </div>
          </div>

          <svg
            width="32"
            height="32"
            viewBox="0 0 32 32"
            fill="currentcolor"
            xmlns="http://www.w3.org/2000/svg"
            class="change-path-svg"
            @click="changePath"
          >
            <path
              d="M16 32C24.8366 32 32 24.8366 32 16C32 7.16344 24.8366 0 16 0C7.16344 0 0 7.16344 0 16C0 24.8366 7.16344 32 16 32Z"
              fill="currentcolor"
            />
            <path
              d="M16.7794 20.4062H19.0938C19.508 20.4062 19.8438 20.742 19.8438 21.1562C19.8438 21.5705 19.508 21.9062 19.0938 21.9062H14.9688C14.5545 21.9062 14.2188 21.5705 14.2188 21.1562V17.0312C14.2188 16.617 14.5545 16.2812 14.9688 16.2812C15.383 16.2812 15.7188 16.617 15.7188 17.0312V19.3456L20.6259 14.4384C20.9188 14.1455 21.3937 14.1455 21.6866 14.4384C21.9795 14.7313 21.9795 15.2062 21.6866 15.4991L16.7794 20.4062ZM15.2206 11.5938H12.9062C12.492 11.5938 12.1562 11.258 12.1562 10.8438C12.1562 10.4295 12.492 10.0938 12.9062 10.0938H17.0312C17.4455 10.0938 17.7812 10.4295 17.7812 10.8438V14.9688C17.7812 15.383 17.4455 15.7188 17.0312 15.7188C16.617 15.7188 16.2812 15.383 16.2812 14.9688V12.6544L11.3741 17.5616C11.0812 17.8545 10.6063 17.8545 10.3134 17.5616C10.0205 17.2687 10.0205 16.7938 10.3134 16.5009L15.2206 11.5938Z"
              fill="currentcolor"
              class="change-svg-second"
            />
          </svg>

          <div class="search-location"
          :class="isPathDirection ? 'search-location-active' : 'search-location-deactive'"
          >
            <svg
              width="16"
              height="18"
              viewBox="0 0 16 18"
              fill="currentcolor"
              xmlns="http://www.w3.org/2000/svg"
              class="search-location-svg"
            >
              <path
                d="M8.00344 0C4.55996 0 0.959961 2.66087 0.959961 7.04348C0.959961 11.1913 7.22083 17.5304 7.45561 17.7652C7.61213 17.9217 7.76866 18 8.00344 18C8.23822 18 8.39474 17.9217 8.55126 17.7652C8.78605 17.5304 15.0469 11.1913 15.0469 7.04348C15.0469 2.66087 11.4469 0 8.00344 0ZM8.00344 9.3913C6.673 9.3913 5.65561 8.37391 5.65561 7.04348C5.65561 5.71304 6.673 4.69565 8.00344 4.69565C9.33387 4.69565 10.3513 5.71304 10.3513 7.04348C10.3513 8.37391 9.33387 9.3913 8.00344 9.3913Z"
                fill="currentcolor"
              />
              <defs>
                <linearGradient
                  id="paint0_linear_72967_235"
                  x1="8.00344"
                  y1="-9"
                  x2="-9.46901"
                  y2="4.67409"
                  gradientUnits="userSpaceOnUse"
                >
                  <stop stop-color="#BD7AE3" />
                  <stop offset="1" stop-color="#8461C9" />
                </linearGradient>
              </defs>
            </svg>
            <input
              type="text"
              class="input-location"
              placeholder="Enter destination..."
            />
          </div>
        </div>
      </div>
      <div class="date-picker"></div>
      <div class="text-box"></div>
    </div>
  </div>
</template>
<script>
export default {
  name: "search-app",
  data() {
    return {
        isPathDirection: false,
      own_destination: "Your location",
      search_input: null,
      input_one_found: null,
      region: [],
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
  methods: {
    changePath(){
        this.isPathDirection = !this.isPathDirection
    },
    findRegion(e) {
      let input_value = e.target.value;
      this.regions.forEach((element) => {
        // let search_reg = element.toLowerCase
        let found_value = element.match(`${input_value}`);
        this.region = found_value;
        console.log(this.region);
      });
      console.log(input_value);
    },
    deleteSearchInput() {
      this.search_input = null;
    },
    deleteSearchInputOne() {
      this.input_one_found = null;
    },
  },
};
</script>
<style>
.search-container {
  margin: 60px 0 0 120px;
}
.search-container .search-content {
  width: 90%;
  display: flex;
  flex-direction: row;
}
.search-container .search-content .search-bar {
  display: flex;
  flex-direction: column;
  width: 24%;
}

.search-content .search-bar h5 {
  text-transform: uppercase;
  display: inline-block;
  margin: 0;
  font-size: 1rem;
  line-height: 24px;
}
.search-content .search-bar .search-bar-content {
  width: 100%;
  position: relative;
  margin-top: 20px;
}
.search-content .search-bar .search-bar-content .search-input {
  width: 90%;
  height: 42px;
  border: none;
  border-radius: 5px;
  box-shadow: 0 7px 64px rgba(0, 0, 0, 0.07);
  padding: 10px 15px 10px 40px;
  box-sizing: border-box;
  color: #d0c9d6;
  font-size: 0.95rem;
  line-height: 20px;
}
.search-content .search-bar .search-bar-content .search-input:focus {
  outline: none;
  border: 1px solid #ecebed;
  color: #3f3356;
}
.search-content .search-bar .search-bar-content .search-svg-active {
  position: absolute;
  left: 10px;
  top: 10px;
}
.search-content .search-bar .search-bar-content .search-svg-deactive {
  position: absolute;
  left: 10px;
  top: 10px;
  color: #d0c9d6;
}
@keyframes Search {
  0% {
    transform: scale(0);
  }
  50% {
    transform: scale(0.5);
  }
  100% {
    transform: scale(1);
  }
}
.search-content .search-bar .search-bar-content .delete-search-active {
  position: absolute;
  right: 35px;
  top: 15px;
  animation: Search 1s linear;
  cursor: pointer;
}
.search-content .search-bar .search-bar-content .delete-search-deactive {
  position: absolute;
  right: 35px;
  top: 15px;
  height: 0;
}
.search-bar .search-one-bar {
  width: 100%;
  margin-top: 20px;
  position: relative;
}
.search-bar .search-one-bar .search-input-one {
  width: 90%;
  height: 42px;
  border: none;
  border-radius: 5px;
  box-shadow: 0 7px 64px rgba(0, 0, 0, 0.07);
  padding: 10px 15px 10px 35px;
  box-sizing: border-box;
  font-size: 0.95rem;
  line-height: 20px;
}
.search-bar .search-one-bar .search-input-one:focus {
  outline: none;
  border: 1px solid #ecebed;
}
.search-bar .search-one-bar .one-active-search {
  position: absolute;
  left: 10px;
  top: 10px;
}
.search-bar .search-one-bar .one-deactive-search {
  position: absolute;
  left: 10px;
  top: 10px;
  color: #d0c9d6;
}
.search-bar .search-one-bar .one-active-delete {
  position: absolute;
  right: 35px;
  top: 15px;
  animation: Search 1s linear;
  cursor: pointer;
}
.search-bar .search-one-bar .one-deactive-delete {
  position: absolute;
  right: 35px;
  top: 15px;
  height: 0;
}
.search-bar .search-one-bar .wrap-one-active {
  display: flex;
  flex-direction: column;
  text-align: center;
  height: auto;
  background: #ffffff;
  width: 90%;
  border-radius: 5px;
  margin-top: 5px;
  animation: Search 1s;
}
.search-bar .search-one-bar .wrap-one-active span {
  cursor: pointer;
  padding-top: 10px;
  box-sizing: border-box;
  box-shadow: 0 7px 64px rgba(0, 0, 0, 0.07);
}
.search-bar .search-one-bar .wrap-one-deactive {
  height: 0;
  overflow: hidden;
}

.search-container .search-content .direction-form {
  width: 24%;
  margin-left: 20px;
  display: flex;
  flex-direction: column;
}
.search-content .direction-form h5 {
  display: inline-block;
  margin: 0;
  font-size: 1rem;
  text-transform: uppercase;
  line-height: 24px;
}
.search-content .direction-form .direction-container {
  width: 100%;
  display: flex;
  flex-direction: column;
  margin-top: 20px;
  background: #ffffff;
  border-radius: 5px;
  box-shadow: 0 7px 64px rgba(0, 0, 0, 0.07);
  padding: 15px 45px 15px 45px;
  box-sizing: border-box;
  position: relative;
}
.direction-form .direction-container .own-location {
  position: relative;
  width: 100%;
}
.direction-form .direction-container .own-location-active{
    position: absolute;
    bottom: 10px;
}
.direction-container .own-location .location-title {
  width: 100%;
  margin: auto;
  color: #6979f8;
  font-size: 0.95rem;
  line-height: 20px;
}
.direction-container .own-location .location-title .own-location-svg {
  position: absolute;
  left: -30px;
  top: 5px;
}
.direction-container .search-location {
  width: 100%;
  margin-top: 15px;
  border-top: 1px dashed #ecebed;
  position: relative;
}
.direction-container .search-location-active{
    position: absolute;
    top: 10px;
}
.direction-container .search-location .input-location {
  width: 90%;
  height: 36px;
  border: none;
  border-radius: 5px;
  font-size: 0.95rem;
  line-height: 20px;
}
.direction-container .search-location .input-location:focus {
  outline: none;
}
.direction-container .search-location .search-location-svg {
  position: absolute;
  left: -30px;
  top: 10px;
  color: #bd7ae3;
}
.direction-form .direction-container .change-path-svg{
    position: absolute;
    right: 10px;
    top: 35px;
    color: #6979f8;
    cursor: pointer;
}
.direction-form .direction-container .change-path-svg .change-svg-second{
    color: #ffffff;
}
</style>
