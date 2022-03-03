<template>
  <div class="container">
    <!-- 卡片开始 -->
    <div class="mdui-card card mdui-shadow-5" style="height: 470px;">
       <div class="mdui-card-header">
         <h2 style="width:100%; text-align: center;  margin-top: 20px;">请输入你的信息</h2>
      <!-- 卡片内容 -->
      <!-- 姓名输入框 -->
       <div class="mdui-card-content" style=" padding-top: 0;">
        <div class="mdui-textfield mdui-textfield-floating-label">
          <i class="mdui-icon material-icons">&#xe87c;</i>
          <label class="mdui-textfield-label">姓名</label>
          <input class="mdui-textfield-input" type="text" v-model="name"/>
        </div>
        <!-- 学号输入框 -->
        <div class="mdui-textfield mdui-textfield-floating-label">
          <i class="mdui-icon material-icons">&#xe24e;</i>
          <label class="mdui-textfield-label">学号</label>
          <input class="mdui-textfield-input" type="text" v-model="id"/>
        </div>

         <!-- 验证码 -->
       <div class="mdui-textfield mdui-textfield-floating-label">
         <i class="mdui-icon material-icons">&#xe0da;</i>
          <label class="mdui-textfield-label">口令</label>
          <input class="mdui-textfield-input" type="text" v-model="code"/>
        </div>
      </div>
     
      <!-- 卡片的按钮 -->
      <div class="mdui-card-actions cardbtn">
          <button @click="getMessage" class="mdui-btn mdui-btn-raised mdui-ripple mdui-color-pink-a200">生成信息</button>
          <p style="margin-top: 10px;font-size: 10px;">该计算机软件，仅供参考学习</p>
       </div> 
    </div>
    <!-- 卡片结束 -->

  </div>
  </div>
</template>

<script>
export default {
  emits:['inputMessage'],
  data() {
    return {
      name:'',
      id:'',
      code:''
    }
  },
  methods:{
    getMessage(){
      if (this.code=='本人自愿承担使用该软件造成的一切后果和相关责任') {
        this.$emit('inputMessage',this.name,this.id)
      }else{
        alert('你的想法很危险！')
      }
    }
  }
}
</script>

<style>
.container {
  width: 100vw;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
}
.card {
  width: 80vw;
  /* height: 600px; */
}
.cardbtn{
  text-align: center;
}
</style>


