<style lang="scss">

@function toRpx( $input ) {
  @return $input / 5 * 6.8 + rpx;
}

@function maxW() {
  @return 750 + rpx;
}

@function maxH() {
  @return 1200 + rpx;
}
.container {
  height: maxH();
  width: maxW();
  background-color: #88F9E5;
  justify-content: center;
}
.container .threeCardWrapper {
  width: toRpx(461);
  height: toRpx(552);
  margin: toRpx(50) auto auto auto;
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
}
.bgcard {
  color: #B6FBEF;
  background-color: #B6FBEF;
  width: toRpx(415);
  height: toRpx(552);
  border-radius: toRpx(10);
}
.logincard {
  width: toRpx(438);
  height: toRpx(552);
  border-radius: toRpx(10);
  margin-top: toRpx(-542);
  background-color: #fff;
}
.threeCardWrapper .logincard .loginLogo{
  color: #ED2553;
  font-size: toRpx(35);
  padding-left: toRpx(50);
  font-weight: bold;
  font-family: "Calibri", "Franklin Gothic Demi", "Source Sans Pro Black", "Aharoni", "Cooper Black";
  border-left: toRpx(5) solid #ED2553;
  letter-spacing: toRpx(3);
  line-height: toRpx(45);
  height: toRpx(45);
  margin: toRpx(70) 0 toRpx(56) 0;
}
.logincard .interactArea {
  margin: 0 toRpx(50) 0 toRpx(53);
}

.logincard .usernameArea {
  margin-bottom: toRpx(53);
}
.logincard .passwordArea {
  margin-bottom: toRpx(53);
}
.logincard .interactArea label {
  display: block;
  font-family: "Calibri", "Tahoma";
  font-size: toRpx(26);
  font-weight: lighter;
  color: #919191;
  margin-bottom: toRpx(11);
}
.logincard input {
  border-style: none;
  outline: none;
  background-color: #ffffff;
  height: toRpx(11);
  line-height: toRpx(11);
  display: none;
}
.logincard .forgetPassword {
  color: #C7C7C7;
  margin: toRpx(47) auto auto auto;
  text-align: center;
  font-size: toRpx(22);
  font-family: "Arial";
  font-weight: 100;
}
.interactArea .button {
  width: toRpx(239);
  margin: 0 auto;
  text-align: center;
  border: toRpx(3) solid #E7E7E7;
  color: #E3E3E3;
  font-family: "Arial";
  font-size: toRpx(23);
  font-weight: lighter;
  display: flex;
  justify-content: center;
  vertical-align: center;
  padding: toRpx(17) 0;
}
.logincard .progressBar {
  width: 100%;
  height: toRpx(2);
  background-color: #E7E7E7;
}

.registercard.inactive {
  background-color: #ED2553;
  height: toRpx(141);
  width: toRpx(141);
  border-radius: 50%;
  overflow: hidden;
  transform: translate(toRpx(202), toRpx(-501));
}
.regWindowWrapper.inactive {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100%;
  height: 100%;
}
.registercard.inactive .switchButton{
  display: flex;
  justify-content: center;
  width: toRpx(32);
  height: toRpx(32);
  align-items: center;
  transform: rotate(-135deg);
  position: absolute;
}

.registercard.inactive .switchButton .heng{
  transform: rotate(-45deg);
}
.registercard.inactive .switchButton .shu{
  transform: rotate(45deg);
}
.registercard.inactive .switchButton .shu,
.registercard.inactive .switchButton .heng {
  width: toRpx(6);
  height: toRpx(30);
  background-color: #fff;
  transform-origin: center center;
  position: absolute;
}
</style>
<template>
  <view class="container">
    <view class="threeCardWrapper">
      <view class="bgcard"></view>
      <view class="logincard">
        <view class="loginLogo">LOGIN</view>
        <view class="interactArea">
          <view class="usernameArea">
            <label for="username">Username</label>
            <input type="text" id="username">
            <view class="progressBar"></view>
          </view>
          <view class="passwordArea">
            <label for="password">Password</label>
            <input type="text" id="password">
            <view class="progressBar"></view>
          </view>
          <view class="button"><view class="textWrapper">GO</view></view>
          <view class="forgetPassword">Forgot your password?</view>
        </view>
      </view>
      <view class="registercard inactive">
        <view class="regWindowWrapper inactive">
          <view class="registerLogo"></view>
          <view class="switchButton" class="switchButton">
            <view class="heng"></view>
            <view class="shu"></view>
          </view>
          <view class="innerMask"></view>
        </view>
      </view>
    </view>
  </view>
</template>

<script>
import wepy from 'wepy'

export default class Index extends wepy.page {
  config = {
    navigationBarTitleText: '全栈工坊'
  }
  components = {

  }

  mixins = []

  data = {}

  computed = {}

  events = {}

  methods = {}

  onLoad() {}
}
</script>

