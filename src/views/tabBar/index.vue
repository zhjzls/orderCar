<template>
  <div class="tab-bar-box">
    <mt-tabbar class="mint-tabbar is-fixed">
      <router-link to="/foo/index">
        <mt-tab-item id="tab1">
          <img slot="icon" src="@/assets/icons/icon.png" />
          tab1
        </mt-tab-item>
      </router-link>
      <router-link to="/bar/index">
        <mt-tab-item id="tab2">
          <img slot="icon" src="@/assets/icons/icon.png" />
          tab2
        </mt-tab-item>
      </router-link>
      <router-link to="/foo1">
        <mt-tab-item id="tab3">
          <img slot="icon" src="@/assets/icons/icon.png" />
          tab3
        </mt-tab-item>
      </router-link>
      <router-link to="/bar2">
        <mt-tab-item id="tab4">
          <img slot="icon" src="@/assets/icons/icon.png" />
          tab4
        </mt-tab-item>
      </router-link>
    </mt-tabbar>
    <router-view></router-view>
  </div>
</template>

<script>
import { Tabbar, TabItem } from "mint-ui";
import icon from "@/assets/icons/icon.png";
export default {
  data() {
    return {
      name: "tabBar",
      icon
    };
  }
};
</script>

<style lang="scss" scoped>
.tab-bar-box {
  height: 10vh;
}
.mint-tabbar {
  background-image: -webkit-linear-gradient(
    top,
    #d9d9d9,
    #d9d9d9 50%,
    transparent 50%
  );
  background-image: linear-gradient(
    180deg,
    #d9d9d9,
    #d9d9d9 50%,
    transparent 50%
  );
  background-size: 100% 1px;
  background-repeat: no-repeat;
  background-position: top left;
  position: relative;
  background-color: #fafafa;
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  right: 0;
  bottom: 0;
  left: 0;
  position: absolute;
  text-align: center;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
}
.mint-tabbar > .mint-tab-item {
  width: 20vw;
  overflow: hidden;
  img {
    // width: 80px;
    height: 80px;
  }
}
.mint-tabbar > .mint-tab-item.is-selected {
  background-color: #eaeaea;
  color: #26a2ff;
}
.mint-tabbar.is-fixed {
  right: 0;
  bottom: 0;
  left: 0;
  position: fixed;
  z-index: 1;
}
</style>