<template>
  <div class="background">
    <div class="shop">
      <landscape-banner></landscape-banner>
      <component :is="layout">
        <router-view />
      </component>
    </div>
  </div>
</template>

<script>
import "ant-design-vue/dist/antd.css";
import LandscapeBanner from "@/components/LandscapeBanner";

// eslint-disable-next-line vue/no-export-in-script-setup
export default {
  components: { LandscapeBanner },
  computed: {
    layout() {
      return this.$route.meta.layout;
    },
  },
};
</script>
<style>
.background {
  background: rgb(45, 37, 58);
  background: -moz-linear-gradient(
    0deg,
    rgba(45, 37, 58, 1) 49%,
    rgba(8, 182, 222, 1) 64%,
    rgba(55, 33, 131, 1) 100%
  );
  background: -webkit-linear-gradient(
    0deg,
    rgba(45, 37, 58, 1) 49%,
    rgba(8, 182, 222, 1) 64%,
    rgba(55, 33, 131, 1) 100%
  );
  background: linear-gradient(
    0deg,
    rgba(45, 37, 58, 1) 49%,
    rgba(8, 182, 222, 1) 64%,
    rgba(55, 33, 131, 1) 100%
  );
  filter: progid:DXImageTransform.Microsoft.gradient(startColorstr="#2d253a",endColorstr="#372183",GradientType=1);
  transition: background 0.5s ease;
}
.shop {
  max-width: 100vw;
  min-height: 200vh;
  background-repeat: no-repeat;
  background-size: 100%;
  transition: background 0.5s ease;
  overflow-x: hidden;
}
/*.change-theme {*/
/*  position: fixed;*/
/*  bottom: 2vh;*/
/*  right: 2%;*/
/*}*/
a:active, /* активная/посещенная ссылка */
a:hover,  /* при наведении */
a {
  text-decoration: none;
  color: #666 !important;
}
input:focus {
  outline: none;
}
</style>
