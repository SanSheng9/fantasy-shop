<template>
  <section>
    <img src="@/assets/2.png" id="back" alt="" />
    <img src="@/assets/1.png" id="front" alt="" />
    <div id="block" class="block">
      <div id="text">Fantasy shop!</div>
      <button id="button">Click me!</button>
    </div>
    <img src="@/assets/sun.png" id="sun" alt="sun" />
  </section>
</template>

<script>
import "ant-design-vue/dist/antd.css";

export default {
  name: "LandscapeBanner",
  created() {
    window.addEventListener("scroll", this.handleScroll);
  },
  unmounted() {
    window.removeEventListener("scroll", this.handleScroll);
  },
  methods: {
    handleScroll() {
      let sky = document.getElementById("sun");
      let front = document.getElementById("front");
      let back = document.getElementById("back");
      let block = document.getElementById("block");

      let value = window.scrollY;
      sky.style.left = value * 0.2 + "px";
      back.style.top = value * 0.2 + "px";
      front.style.top = value * 0.3 + "px";
      block.style.marginTop = value * 1.1 + "px";
      if (value >= 780) {
        block.style.zIndex = 9;
      } else {
        block.style.zIndex = 11;
      }
    },
  },
};
</script>

<style scoped>
section {
  position: relative;
  width: 100%;
  height: 100vh;
  padding: 100px;
}
section img {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  object-fit: cover;
}
.block {
  position: absolute;
  left: 36vw;
  z-index: 11;
  display: flex;
  flex-direction: column;
  align-content: space-between;
  min-height: 400px;
  align-items: center;
  justify-content: space-between;
}
#text {
  color: #eeeeee;
  white-space: nowrap;
  font-size: 6em;
  font-weight: 800;
  box-shadow: white;
  text-transform: uppercase;
}
#button {
  font-size: 3em;
  padding: 8px 30px;
  font-weight: 800;
  color: rgb(45, 37, 58);
  background-color: #eeeeeeff;
  border: none;
  border-radius: 40px;
  text-decoration: none;
  cursor: pointer;
}
#front {
  z-index: 10;
  margin-top: 285px;
}
#back {
  z-index: 6;
}
section #sun {
  z-index: 1;
}
</style>
