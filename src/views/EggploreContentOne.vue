<template>
  <div class="content-one-container">
    <h2>Components</h2>
    <div class="content-one-content">
      <h3>Buttons</h3>
      <hr />
      <div class="content-one-buttons">
        <div class="button-blog-one common">
          <h5>Large Buttons</h5>
          <button class="blog-button-one">Default</button>
          <button class="blog-button-two">Ghost</button>
          <button class="blog-button-three">
            <svg
              width="14"
              height="14"
              viewBox="0 0 14 14"
              fill="none"
              xmlns="http://www.w3.org/2000/svg"
            >
              <path
                d="M7 0C3.15 0 0 3.15 0 7C0 10.85 3.15 14 7 14C10.85 14 14 10.85 14 7C14 3.15 10.85 0 7 0ZM10.5 7.875H7.875V10.5H6.125V7.875H3.5V6.125H6.125V3.5H7.875V6.125H10.5V7.875Z"
                fill="white"
              />
            </svg>
            Left icon
          </button>
        </div>
        <div class="button-blog-two common">
          <h5>Small buttons</h5>
          <button class="blog-button-four">Small Default</button>
          <button class="blog-button-five">Small Ghost</button>
          <button class="blog-button-six">
            <svg
              width="14"
              height="14"
              viewBox="0 0 14 14"
              fill="none"
              xmlns="http://www.w3.org/2000/svg"
            >
              <path
                d="M7 0C3.15 0 0 3.15 0 7C0 10.85 3.15 14 7 14C10.85 14 14 10.85 14 7C14 3.15 10.85 0 7 0ZM10.5 7.875H7.875V10.5H6.125V7.875H3.5V6.125H6.125V3.5H7.875V6.125H10.5V7.875Z"
                fill="white"
              />
            </svg>
            Small Icon
          </button>
        </div>
        <div class="button-blog-three">
          <h5>Other buttons</h5>
            <div class="wrapper-buttons">
                <button class="svg-button">
            <svg
              width="24"
              height="24"
              viewBox="0 0 24 24"
              fill="none"
              xmlns="http://www.w3.org/2000/svg"
            >
              <path
                d="M3.76886 9.04941L17.596 5.09879C18.3861 4.90126 19.0775 5.59262 18.88 6.38274L14.9294 20.2099C14.6331 21.0988 13.4479 21.1976 13.0528 20.3087L10.2874 13.7901L3.76886 11.0247C2.7812 10.5309 2.87997 9.34571 3.76886 9.04941Z"
                fill="white"
              />
            </svg>
            
          </button>
          <div class="other-left-btn">
                <button class="circle-btn">
                    <div class="circle-loader"></div>
                </button>
            </div>
            </div>
          
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "eggplore-content-one",
};
</script>
<style>
.content-one-container {
  display: flex;
  flex-direction: column;
  margin: 40px 0 0 120px;
}
.content-one-container h2 {
  text-transform: uppercase;
  color: #6979f8;
  line-height: 30px;
  border-left: 5px solid #6979f8;
  padding-left: 10px;
  box-sizing: border-box;
}
.content-one-container .content-one-content {
  width: 90%;
}

.content-one-content .content-one-buttons {
  display: flex;
  flex-direction: row;
  width: 100%;
}
.content-one-content h3 {
  text-transform: uppercase;
  line-height: 30px;
}
.content-one-content .content-one-buttons .common {
  width: 31%;
  display: flex;
  flex-direction: column;
}
.content-one-content .content-one-buttons .button-blog-three {
  width: 31%;
  display: flex;
  flex-direction: column;
}
.content-one-content .content-one-buttons .common h5 {
  line-height: 24px;
  text-transform: uppercase;
  font-size: 1rem;
  display: inline-block;
  margin: 35px 0 0 0;
}
.content-one-content .content-one-buttons .button-blog-three h5 {
  line-height: 24px;
  text-transform: uppercase;
  font-size: 1rem;
  display: inline-block;
  margin: 35px 0 0 0;
}
.content-one-buttons .button-blog-one button {
  width: 65%;
  margin-top: 30px;
  height: 42px;
}
.button-blog-one .blog-button-one {
  background: #be52f2;
  border: none;
  border-radius: 5px;
  color: #ffffff;
  text-transform: uppercase;
  font-size: 1rem;
}
.button-blog-one .blog-button-two {
  color: #6979f8;
  border: 2px solid #6979f8;
  border-radius: 5px;
  background: #ffffff;
  font-size: 1rem;
  text-transform: uppercase;
}
.button-blog-one .blog-button-three {
  background: #6979f8;
  border: none;
  border-radius: 5px;
  text-transform: uppercase;
  font-size: 1rem;
  color: #ffffff;
}
.button-blog-two button {
  width: 35%;
  margin-top: 30px;
  height: 28px;
}
.button-blog-two .blog-button-four {
  background: #6979f8;
  border: none;
  border-radius: 5px;
  color: #ffffff;
  font-size: 0.85rem;
}
.button-blog-two .blog-button-five {
  background: #ffffff;
  border: 2px solid #6979f8;
  border-radius: 5px;
  color: #6979f8;
  font-size: 0.85rem;
}
.button-blog-two .blog-button-six {
  background: #be52f2;
  border: none;
  border-radius: 5px;
  font-size: 0.85rem;
  color: #ffffff;
}
.button-blog-three .svg-button{
    width: 12%;
    height: 42px;
    background: #6979f8;
    margin-top: 30px;
    border: none;
    border-radius: 15px;
}
.button-blog-three .other-left-btn{
    display: flex;
    flex-direction: column;
    width: 100%;
}
@keyframes spin{
    0% {transform: rotate(0deg);}
    100% {transform: rotate(360deg);}
}
.button-blog-three .other-left-btn .circle-btn{
    display: block;
    width: 50%;
    margin-top: 30px;
    margin-left: 25px;
    background: #6979f8;
    justify-items: center;
    height: 42px;
    border: none;
    border-radius: 5px;
}
.button-blog-three .wrapper-buttons{
    display: flex;
    flex-direction: row;
    width: 100%;
}
.circle-btn .circle-loader{


    /* border: 12px solid #6979f8;
    border-radius: 50%;
    border-top: 12px solid #FFFFFF;
    width: 6px;
    height: 6px;
    animation: spin 2s linear infinite;
    margin: auto; */

}
</style>
