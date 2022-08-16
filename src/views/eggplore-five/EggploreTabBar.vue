<template>
  <div class="eggplore-tabbar-container">
    <h5>Tab</h5>
    <div class="tabbar-content">
      <div class="tabbar" ref="tabChild"></div>
      <svg
        width="47"
        height="3"
        viewBox="0 0 47 3"
        fill="currentcolor"
        xmlns="http://www.w3.org/2000/svg"
      >
        <path
          d="M0 3C0 1.34315 1.34315 0 3 0H44C45.6569 0 47 1.34315 47 3H0Z"
          fill="currentcolor"
        />
      </svg>
    </div>
  </div>
</template>
<script>
export default {
  name: "eggplore-tabbar",
  mounted() {
    this.getTabChild();
    this.addTabClass();
  },
  methods: {
    getTabChild() {
      let tab_child = this.$refs.tabChild;
      for (let i = 0; i < 4; i++) {
        const btn = document.createElement("button");
        tab_child.appendChild(btn);
        this.addClassButton(btn);
      }
      tab_child.firstChild.classList.add("default-active");
    },
    addTabClass() {
      let tab_child = this.$refs.tabChild;
      if (tab_child.childElementCount) {
        let childs = tab_child.childNodes;
        childs.forEach((element) => {
          if (element.classList.contains("default-active")) {
            element.innerText = "Active";
          } else {
            element.innerText = "InActive";
          }
        });
      }
    },
    addClassButton(btn) {
      btn.addEventListener("click", () => {
        if (btn.classList.contains("tab-btn-active")) {
          btn.classList.remove("tab-btn-active");
        } else {
          btn.classList.add("tab-btn-active");
        }
      });
      console.log(btn);
    },
  },
};
</script>
