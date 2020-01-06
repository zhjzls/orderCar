<template>
  <div class="tab-bar-box">
    <mt-tabbar class="mint-tabbar is-fixed">
      <router-link to="/orderCar/index">
        <mt-tab-item id="orderCar">
          <img slot="icon" src="@/assets/icons/icon.png" />
          orderCar
        </mt-tab-item>
      </router-link>
      <router-link to="/user-list/index">
        <mt-tab-item id="user-list">
          <img slot="icon" src="@/assets/icons/icon.png" />
          user-list
        </mt-tab-item>
      </router-link>

      <router-link to="/personal/index">
        <mt-tab-item id="personal">
          <img slot="icon" src="@/assets/icons/icon.png" />
          personal
        </mt-tab-item>
      </router-link>
    </mt-tabbar>
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
  background-color: #e7d4d4;
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
  justify-content: space-around;
  align-items: center;
  text-align: center;
}
.mint-tabbar .mint-tab-item {
  width: 30vw;
  overflow: hidden;
  img {
    height: 4vh;
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