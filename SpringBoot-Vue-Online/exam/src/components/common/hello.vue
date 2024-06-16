<template>
  <section class="index">
    <div class="hello">
      <i class="iconfont icon-xihuan"></i><span>很高兴遇见你,{{user.userName}}老师。</span>
    </div>
    <div class="msg">
      <p class="title">教务公告：</p>
      <ul>
        <li @click="openMsg()"><i class="iconfont icon-flag"></i>7月实习通知</li>
        <li @click="openMsg1()"><i class="iconfont icon-flag"></i>18号的考试安排</li>
        <li @click="openMsg2()"><i class="iconfont icon-flag"></i>关于答辩具体流程</li>
      </ul>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      user: { //用户信息
        userName: null,
        userId: null
      }
    }
  },
  created() {
    this.getUserInfo()
  },
  methods: {
    getUserInfo() { //获取用户信息
      let userName = this.$cookies.get("cname")
      let userId = this.$cookies.get("cid")
      this.user.userName = userName
      this.user.userId = userId
    },
    openMsg() {
      this.$alert('根据湘潭大学规定，计算机学院的学生将于7月1号开始实习，持续时间等待后续通知，实习期间在带队老师的安排下开展实习。','7月实习通知',{
        confirmButtonText: '确定'
      })
    },
    openMsg1() {
      this.$alert('根据湘潭大学规定，计算机学院计算机科学与技术1班的学生将于6月18号进行软件工程的考试，具体时间等待后续通知。','18号的考试安排',{
        confirmButtonText: '确定'
      })
    },
    openMsg2() {
      this.$alert('根据湘潭大学规定，计算机学院计算机科学与技术1班的学生将于6月18号之后进行软件设计实践的答辩，具体时间等待后续通知。','关于答辩时间安排',{
        confirmButtonText: '确定'
      })
    }
  }
}
</script>


<style lang="less" scoped>
.index {
  margin-left: 70px;
  .hello {
    font-size: 20px;
    color: #726f70;
    .icon-xihuan {
      font-size: 30px;
      color: #dd6572;
    }
  }
  .msg {
    .title {
      font-size: 16px;
      color: #000;
      margin-top: 20px;
      margin-left: 10px;
    }
    ul {
      display: flex;
      flex-direction: column;
      width: 200px;
      overflow: hidden;
    }
    li {
      margin-top: 10px;
      font-size: 14px;
      color: lightcoral;
      cursor: pointer;
      display: inline-block;
    }
  }
}
</style>

