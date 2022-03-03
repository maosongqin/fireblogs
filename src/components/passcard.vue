<template>
  <div class="container">
    <!-- 卡片开始 -->
    <div class="mdui-card card mdui-shadow-4" style=" height:390px">
      <!-- 布局容器开始 -->
      <div class="mdui-container-fluid">
        <!-- 标题开始 -->
        <div class="mdui-row">
          <div class="mdui-col-xs-12">
            <h2 class="card-title">广州城市理工学院出入审批凭证</h2>
          </div>
        </div>
        <!-- 标题结束 -->

        <!-- 主体开始 -->
        <div class="mdui-row">
          <!-- 左边的个人信息开始 -->
          <div class="mdui-col-xs-6" style="margin-top: 20px">
            <ul class="list">
              <li>{{name}}</li>
              <li>计算机工程学院</li>
              <li>{{id}}</li>
              <li>单据审批状态：</li>
              <li class="mark"><strong style="font-size: 22px;">同意</strong></li>
            </ul>
          </div>
          <!-- 左边的个人信息结束 -->
          <!-- 右边信息开始 -->
          <div class="mdui-col-xs-6" style="margin-top: 20px">
            <ul>
              <li>离校时间：</li>
              <li><strong style="font-size:20px">{{departingTime}}</strong></li>
              <li style="margin-bottom: 0;">
                <img src="../assets/img.png" alt="">
              </li>
            </ul>
          </div>
          <!-- 右边信息结束 -->
        </div>
        <!-- 主体结束 -->

        <!-- 离校状态开始 -->
        <div class="mdui-row">
          <div class="mdui-col-xs-12">
            <h4 style="text-align: center; margin-top: 10px">离校</h4>
          </div>
        </div>
        <!-- 离校状态结束 -->

        <!-- 动态时间开始 -->
        <div class="mdui-row">
          <div class="mdui-col-xs-12">
            <h3 style="text-align: center; margin-top: 20px">{{ nowTime }}</h3>
          </div>
        </div>
        <!-- 动态时间结束 -->
      </div>
      <!-- 布局容器结束 -->
    </div>
    <!-- 卡片结束 -->
    <p class="bottom-information">
      Copyright(C) 2021 广州城市理工学院网络与信息中心 版权所有
    </p>
  </div>
</template>

<script>
export default {
  props: ['name',"id"],
  data() {
    return {
      nowTime: "2021-11-13 12:08:25",
      departingTime:"2021-11-13"
    };
  },
  mounted() {
    

     Date.prototype.format = function (fmt) {
        var o = {
          "y+": this.getFullYear, //年
          "M+": this.getMonth() + 1, //月份
          "d+": this.getDate(), //日
          "h+": this.getHours(), //小时
          "m+": this.getMinutes(), //分
          "s+": this.getSeconds(), //秒
        };
        if (/(y+)/.test(fmt))
          fmt = fmt.replace(
            RegExp.$1,
            (this.getFullYear() + "").substr(4 - RegExp.$1.length)
          );
        for (var k in o)
          if (new RegExp("(" + k + ")").test(fmt))
            fmt = fmt.replace(
              RegExp.$1,
              RegExp.$1.length == 1
                ? o[k]
                : ("00" + o[k]).substr(("" + o[k]).length)
            );
        return fmt;
      };

    this.departingTime=(new Date()).format('yyyy-MM-dd')
    
    setInterval(() => {
       this.nowTime=(new Date()).format('yyyy-MM-dd hh:mm:ss')
    }, 1000);

  },
};
</script>

<style>
.container {
  width: 100vw;
  height: 100vh;
}
.card {
  width: 90vw;
  height: 45vh;
  position: absolute;
  top: 30px;
  padding: 0 30px 0 30px;
}
.bottom-information {
  display: inline;
  position: relative;
  top: 72px;
  font-size: 11px;
  padding: 0 5vw 0 5vw;
}
.card-title {
  margin-top: 30px;
  text-align: center;
  font-size:20px
}
ul {
  list-style: none;
}
li:not(.mark) {
  margin-bottom: 14px;
}
li:nth-child(5) {
  text-align: center;
  color: #2af12b;
  font-size: 16px;
}
img {
  display: block;
  transform: translateX(-8px);
  width: 30vw;
}
</style>
