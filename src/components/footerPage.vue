<template>
  <div class="footer-box">
    <div class="pc-footer">
      <div class="footer-row1">
        <div class="row1-col">
          <div class="col-text">关于</div>
          <div class="col-text1">关于我们</div>
          <div class="col-text1">服务范围</div>
          <div class="col-text1">经典案例</div>
          <div class="col-text1">合作伙伴</div>
        </div>
        <div class="row1-col">
          <div class="col-text">联系我们</div>
          <div class="col-text1 qq_icon">QQ：1808569213</div>
          <div class="col-text1 email_icon">邮箱：1808569213@qq.com</div>
          <div class="col-text1 wx_icon">微信号：18428088011</div>
        </div>
        <div class="row1-col2 row1-col2-logo">
          <div class="logo-text">极越科技</div>
        </div>
        <div class="row1-col">
          <div>报价咨询热线 <span style="font-size: 12px;">（8:00-22:00）</span></div>
          <div class="col-text1 phone_icon">18428088011</div>
          <div class="col-text1" style="color: #ffffff;font-weight: 100;font-size: 12px;">联系人：尹先生</div>
          <div class="col-text1" style="color: #ffffff;font-weight: 100;font-size: 12px;" v-html="'&nbsp; &nbsp; 地址：成都市高新西区红旗大道北段146号'"></div>
        </div>
      </div>
    </div>
    <div class="mobile-footer"></div>
    <div class="bootom-footer">Copyright © 2008 - 2014 NB科技有限公司 All Right Reserved.</div>
  </div>
</template>
<script>
export default {
  name: 'Footerbox'
}
</script>
<style scoped>
.footer-box {
  width: 100%;
  padding-top: 20px;
  background: url('./img/footerbg.png') no-repeat center;
  background-size: 100% 100%;
}
.footer-row1 {
  position: relative;
  border-bottom: 1px solid #000;
  padding-bottom: 20px;
}
.pc-footer .row1-col {
  display: inline-block;
  padding: 0 50px;
  text-align: left;
  vertical-align: text-top;
}
.footer-row1 .row1-col2 {
  height: 100%;
  display: inline-block;
  padding: 0 30px;
  vertical-align: inherit;
}
.bootom-footer {
  color: #7c8590;
  width: 100%;
  font-size: 12px;
  transform: scale(1);
  padding: 8px 0;
  background: rgba(34, 34, 34, .5);
  border-top: 1px solid #444;
}
.col-text {
  color: #ffffff;
  font-size: 16px;
  padding: 2px 0;
}
.col-text1 {
  padding: 2px 0;
  color: #7c8590;
  font-size: 14px;
  font-weight: 600;
  position: relative;
}
.col-text1::after {
  content: '';
  display: inline-block;
  width: 15px;
  height: 15px;
  position: absolute;
  left: -20px;
  top: 0;
  bottom: 0;
  margin: auto;
}
.row1-col2-logo {
  display: inline-block;
  width: 250px;
  text-align: center;
  position: relative;
}
.logo-text {
  font-size: 30px;
  font-weight: 500;
  position: absolute;
  left: 100px;
  top: 20px;
}
.logo-text::after {
  content: '';
  display: inline-block;
  width: 65px;
  height: 73px;
  position: absolute;
  left: -70px;
  top: 0;
  bottom: 0;
  margin: auto;
  background: url('./img/footerlogo.png') no-repeat center;
}
.qq_icon::after {
  background: url(./img/pic_qq.png) no-repeat center;
}
.email_icon::after {
  background: url(./img/pic_email.png) no-repeat center;
}
.wx_icon::after {
  background: url(./img/pic_wechat.png) no-repeat center;
}
.phone_icon {
  font-size: 30px;
  color: #518de4;
  padding-left: 30px;
}
.phone_icon::after {
  width: 65px;
  height: 73px;
  background: url(./img/icon_phone.png) no-repeat center;
}

</style>
