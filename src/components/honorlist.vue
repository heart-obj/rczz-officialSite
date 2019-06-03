<template>
  <div>
    <div class="box1">
      <div class="text-title1">Honorary certificate</div>
      <div class="text-title2">
        <span class="line line1"></span>
        <span class="text">荣誉资质</span>
        <span class="line line2"></span>
      </div>
      <div class="text-title3">资质证明我们很优秀</div>
      <div class="text-title4">
        极越科技的早期核心团队成立至今已经有九年多了，从2010年成立创业团队，到升级为工作室，再到注册成立公司，我们一步一步的发展见证了客户对我们服务的满意，反应了市场对我们实力的认可。并获得了诸多的荣誉！
      </div>
      <div class="row justify-content-center" style="padding:8vw 0">
        <div style="display:inline-block;margin: 0 1.5vw;" v-for="(item, i) in honorlist" :key="i" class="justify-col">
          <div class="img-icon" :style="{background: 'url('+ item.imgurl +') no-repeat center', 'background-size': '100% 100%'}"></div>
          <span style="color:#050000;font-size:14px;font-weight:bold;margin-top:0.15vw;">{{item.label}}</span>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: 'Honor', // 荣誉资质
  data () {
    return {
      honorlist: [
        {
          label: '四川省优秀互联网企业证书',
          imgurl: './static/img/honor1.png'
        },
        {
          label: '成都市创新创业优秀企业',
          imgurl: './static/img/honor2.png'
        },
        {
          label: '电子科技大学校企合作单位',
          imgurl: './static/img/honor3.png'
        },
        {
          label: '智城外包平台指定服务商',
          imgurl: './static/img/honor4.png'
        },
        {
          label: '网易云信西南地区高级合作伙伴',
          imgurl: './static/img/honor5.png'
        }
      ]
    }
  }
}
</script>
<style scoped>
.box1 {
  width: 100%;
}
.box1 .text-title1 {
  font-size: 1.5vw;
  font-weight: bold;
  color: #dddddd;
}
.box1 .text-title2 {
  font-size: 1.9vw;
  color: #499aff;
  font-weight: bold;
  position: relative;
  display: flex;
  justify-content: center;
}
.box1 .text-title2 .text{
  font-size: 1.9vw;
  color: #499aff;
  font-weight: bold;
  vertical-align: middle;
  padding: 0 10px;
}
.box1 .text-title2 .line {
  display: inline-block;
  width: calc(50% - 100px);
  height: 1px;
  border: 1px solid #dcdcdc;
}
.box1 .text-title2 .line1 {
  position: absolute;
  top: 50%;
  left: 0;
  margin-top: -0.5px;
}
.box1 .text-title2 .line2 {
  position: absolute;
  top: 50%;
  right: 0;
  margin-top: -0.5px;
}
.box1 .text-title3 {
  color: #333333;
  font-size: 0.73vw;
}
.box1 .text-title4 {
  display: inline-block;
  box-sizing: border-box;
  padding: 1.56vw 15.6vw 0 15.6vw;
  color: #999999;
  font-size: 0.8vw;
}
.box1 .row {
  margin: 0;
}
.box1 .img-icon {
  width: 14.1vw;
  height: 9.3vw;
}
.justify-col {
  width: 14.1vw;
}
@media screen and (max-width: 1200px) {
  .justify-col {
    width: 30%;
  }
  .box1 .img-icon {
    width: 100%;
    height: 20vw;
  }
}
</style>
