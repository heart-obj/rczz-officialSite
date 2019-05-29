<template>
  <div>
    <div class="box1">
      <div class="text-title1">Cooperative partner</div>
      <div class="text-title2">
        <span class="line line1"></span>
        <span class="text">合作伙伴</span>
        <span class="line line2"></span>
      </div>
      <div class="text-title3">与中外实力企业取得合作</div>
      <div class="text-title4">
        我们服务过的客户遍布中国内地、港台、新加坡、日本、澳大利亚、柬埔寨、美国和英国等全球各地，在帮助客户提供方案解决、<br/>
        美工设计、软件开发、产品运维、服务代办、技术支持等方面具有明显优势。
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: 'CooperativePartner', // 合作伙伴
  data () {
    return {}
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
</style>
