<template>
  <div class="order-container">
    <h1>约车</h1>
    <h3>当前时间： {{nowTime}}</h3>

    <div style="padding: 12px">
      <el-row :gutter="12">
        <el-col style="margin: 5px 0" :xs="24" :sm="12" :md="8" :lg="6" v-for="(item, index) in timeList" :key="index" :offset="0">
          <el-card :body-style="{ margin: '12px 0' }">
            <!-- <img
              src="https://shadow.elemecdn.com/app/element/hamburger.9cf7b091-55e9-11e9-a976-7f4d0b07eef6.png"
              class="image"
            /> -->
            <div style="padding: 14px;">
              <span>{{item.timeRange}}</span>
              <div class="bottom clearfix">
                  <div v-if="item.username==='xxxd'">
                      <el-button size="small" class="button" type="success" :disabled="true">预约成功</el-button> <el-button size="small" type="warning">取消预约</el-button>
                  </div>
                <el-button v-else size="small" class="button" :type="item.selected ? 'danger' : 'primary'" :disabled="item.selected">{{item.selected ? "不可预约" : "预约"}}</el-button>
              </div>
            </div>
          </el-card>
        </el-col>
      </el-row>
    </div>

    <ul>
      <li v-for="(timeRange, index) in timeList" :key="index">{{ timeRange }}</li>
    </ul>
  </div>
</template>

<script>
import moment from "moment";
export default {
  data() {
    return {
      name: "orderCar",
      nowTime: "",
      timer: null,
      timeList: [
          {timeRange: "8:00-8:30", selected: false, username:'xxxa' },
          {timeRange: "8:30-9:00", selected: true, username:'xxxb' },
          {timeRange: "9:00-9:30", selected: false, username:'xxxc' },
          {timeRange: "9:30-10:00", selected: true, username:'xxxd' },
          {timeRange: "10:00-10:30", selected: false, username:'xxxe' },
          {timeRange: "10:30-11:00", selected: false, username:'xxxa' }
      ]
    };
  },
  methods: {
    getNowTime() {
      this.nowTime = moment().format("YYYY-MM-DD HH:mm:ss");
    }
  },
  mounted() {
    this.getNowTime();
    this.timer = setInterval(() => {
      this.getNowTime();
    }, 1000);
  },
  destroyed() {
    clearInterval(this.timer);
  }
};
</script>

<style lang="scss" scoped>
.order-container {
  h1,
  h2,
  h3,
  p {
    text-align: center;
  }
  & > div {
    text-align: center;
  }

    .time {
    font-size: 13px;
    color: #999;
  }
  
  .bottom {
    margin-top: 13px;
    line-height: 12px;
  }

  .image {
    width: 100%;
    display: block;
  }

  .clearfix:before,
  .clearfix:after {
      display: table;
      content: "";
  }
  
  .clearfix:after {
      clear: both
  }
}
</style>