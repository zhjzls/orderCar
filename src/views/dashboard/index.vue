<template>
  <div class="dashboard-container">
    <div class="dashboard-text">name: {{ name }}</div>
      <!-- <router-view></router-view> -->

    <Tabbar class="tab-bar" v-model="selected">
      <TabItem class="tab-item" id="首页">
        <router-link to="/dashboard/index">首页</router-link>
      </TabItem>
      <!-- <TabItem class='tab-item' id='约车'><router-link to="/orderCar">约车</router-link></TabItem> -->
      <TabItem class="tab-item" id="个人中心">
        <router-link to="/dashboard/personal">个人中心</router-link>
      </TabItem>
    </Tabbar>
  </div>
</template>

<script>
import { mapGetters } from "vuex";
import { Tabbar, TabItem } from "mint-ui";
export default {
  name: "Dashboard",
  components: {
    Tabbar,
    TabItem
  },
  computed: {
    ...mapGetters(["name"])
  }
};
</script>

<style lang='scss' scoped>
.dashboard {
  &-container {
    // margin: 30px;
    height: calc(100vh - 50px);
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    .tab-bar {
      display: flex;
      flex-direction: row;
      justify-content: space-between;

      .tab-item {
        width: 25vw;
        height: 60px;
        line-height: 60px;
        text-align: center;
      }
    }
  }
  &-text {
    font-size: 30px;
    line-height: 46px;
  }
}
</style>
