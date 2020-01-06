<template>
  <div>
    <mt-tabbar class="mint-tabbar is-fixed" v-model="selected">
      <mt-tab-item id="tab1">
        <img slot="icon" src="@/assets/icons/icon.png" />
        tab1
      </mt-tab-item>
      <mt-tab-item id="tab2">
        <img slot="icon" src="@/assets/icons/icon.png" />
        tab2
      </mt-tab-item>
      <mt-tab-item id="tab3">
        <img slot="icon" src="@/assets/icons/icon.png" />
        tab3
      </mt-tab-item>
      <mt-tab-item id="tab4">
        <img slot="icon" src="@/assets/icons/icon.png" />
        tab4
      </mt-tab-item>
    </mt-tabbar>
    <router-view :key="key" />
  </div>
</template>

<script>
export default {
  data() {
    return {
      // key: "/foo"
    };
  },
  computed: {
    key() {
      console.log(this.$route.path)
      return this.$route.path;
    }
  }
};
</script>

<style lang="scss" scoped>
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
  display: flex;
  right: 0;
  bottom: 0;
  left: 0;
  position: absolute;
  text-align: center;
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
