<style lang="scss">

@function toRpxNum( $input ) {
  @return $input / 5 * 6.8;
}
@function toRpx( $input ) {
  @return toRpxNum( $input ) + rpx;
}

@function maxW() {
  @return 750 + rpx;
}

@function maxH() {
  @return 1200 + rpx;
}

@function XrotateX( $delta ) {
  $origin: -135;
  @return $origin + $delta + deg;
}
@mixin XposX( $position ) {
  @if $position == "right" {

  }
  @if $position == "openMiddle" {

  }
  @if $position == "closeMiddle" {

  }
  @if $position == "left" {
    transform: translate(513rpx, -102rpx);
  }
}

@mixin widthheight( $width, $height ) {
  height: $height;
  width: $width;
}

@mixin roundCorner($radius: toRpx(10)) {
  border-radius: $radius;
}
@mixin verticalMiddleAlign($height: toRpx(10)) {
  line-height: $height;
  height: $height;
}

$heightBG: toRpxNum(552);
$heightLogin: toRpxNum(552);
$heightRegister: toRpxNum(552);

@function calculateMarginTopRegister() {
  @return $heightRegister * -1 + toRpxNum(10) + rpx;
}

.container {
  @include widthheight( maxW(), maxH() );
  background-color: #88F9E5;
  justify-content: center;

  .threeCardWrapper {
    display: flex;
    flex-wrap: wrap;
    width: toRpx(461);
    height: toRpx(552);
    margin: toRpx(50) auto auto auto;
    justify-content: center;

    .bgcard {
      background-color: #B6FBEF;
      @include widthheight( toRpx(415), toRpx(552) );
      @include roundCorner();
    }

    .logincard {
      width: toRpx(438);
      height: toRpx(552);
      border-radius: toRpx(10);
      margin-top: toRpx(-542);
      background-color: #fff;

      .loginLogo {
        color: #ED2553;
        font-size: toRpx(35);
        padding-left: toRpx(50);
        font-weight: bold;
        font-family: "Calibri", "Franklin Gothic Demi", "Source Sans Pro Black", "Aharoni", "Cooper Black";
        border-left: toRpx(5) solid #ED2553;
        letter-spacing: toRpx(3);
        @include verticalMiddleAlign(toRpx(45));
        margin: toRpx(70) 0 toRpx(56) 0;
      }

      .interactArea {
        margin: 0 toRpx(50) 0 toRpx(53);

        label {
          display: block;
          font-family: "Calibri", "Tahoma";
          font-size: toRpx(26);
          font-weight: lighter;
          color: #919191;
          margin-bottom: toRpx(11);
        }

        input {
          border-style: none;
          outline: none;
          background-color: #ffffff;
          height: toRpx(11);
          line-height: toRpx(11);
          display: none;
        }

        .usernameArea {
          margin-bottom: toRpx(53);
        }

        .passwordArea {
          margin-bottom: toRpx(53);
        }

        .button {
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

        .forgetPassword {
          color: #C7C7C7;
          margin: toRpx(47) auto auto auto;
          text-align: center;
          font-size: toRpx(22);
          font-family: "Arial";
          font-weight: 100;
        }

        .progressBar {
          @include widthheight( 100%, toRpx(2));
          background-color: #E7E7E7;
        }
      }
    }
  }
  .registercard {
    &.inactive {
      background-color: #ED2553;
      @include widthheight( toRpx(141), toRpx(141) );
      border-radius: 50%;
      overflow: hidden;
      transform: translate(toRpx(202), toRpx(-501));
      .regWindowWrapper {
        display: flex;
        justify-content: center;
        align-items: center;
        @include widthheight( 100%, 100% );
        .registerLogo {
        }
        .switchButton {
          display: flex;
          justify-content: center;
          @include widthheight( toRpx(32), toRpx(32));
          align-items: center;
          transform: rotate(-135deg);
          position: absolute;
          .heng, .shu {
            @include widthheight( toRpx(6), toRpx(30) );
            background-color: #fff;
            transform-origin: center center;
            position: absolute;
          }
          .heng {
            transform: rotate(-45deg);
          }

          .shu {
            transform: rotate(45deg);
          }
        }
        .innerMask {

        }
      }
    }
    &.active {
      @include widthheight( toRpx(461), toRpx(552) );
      background-color: #ED2552;
      @include roundCorner();
      // margin-top: -750rpx;
       margin-top: calculateMarginTopRegister();
      .regWindowWrapper {
        @include widthheight( 100%, 100% );
        .registerLogo {
          font-family: "Calibri", "Franklin Gothic Demi", "Source Sans Pro Black", "Aharoni", "Cooper Black";
          font-size: toRpx(37);
          @include verticalMiddleAlign(toRpx(44));
          color: #ffffff;
          margin: toRpx(60) 0 toRpx(40) 0;
          padding-left: toRpx(44);
          border-left: 4px solid white;
        }
        .switchButton {
          display: flex;
          justify-content: center;
          transform: XrotateX(135);
          @include widthheight( toRpx(32), toRpx(32));
          @include XposX("left");
          align-items: center;
          transform: XrotateX(0);
          position: absolute;
          .heng, .shu {
            @include widthheight( toRpx(6), toRpx(30) );
            background-color: #fff;
            transform-origin: center center;
            position: absolute;
          }
          .heng {
            transform: rotate(-45deg);
          }

          .shu {
            transform: rotate(45deg);
          }
        }
        .progressBar {
          @include widthheight( 100%, toRpx(2) );
          background-color: #F77C99;
        }
        .interactArea {
          margin: 0 toRpx(53);
          label {
            display: block;
            width: 100%;
            color: white;
            font-family: "Calibri", "Tahoma";
            font-size: toRpx(26);
            font-weight: lighter;
            margin-bottom: toRpx(18);
          }
          input {
            display: none;
          }
          .usernameArea, .passwordArea {
            margin-bottom: toRpx(54);
          }

          .repeatPasswordArea {
            margin-bottom: toRpx(45);
          }
          .nextButton {
            @include widthheight( 100%, toRpx(72) );
            @include verticalMiddleAlign( toRpx(72) );
            background-color: #fff;
            color: #ED2553;
            font-family: "Arial Unicode MS";
            font-size: toRpx(23);
            text-align: center;
            font-weight: bolder;
          }
        }

      }
    }
  }
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
      <view class="registercard active">
        <view class="regWindowWrapper active">
          <view class="registerLogo">REGISTER</view>
          <view class="switchButton" class="switchButton">
            <view class="heng"></view>
            <view class="shu"></view>
          </view>
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
            <view class="repeatPasswordArea">
              <label for="repeatPasswordArea">Repeat Password</label>
              <input type="text" id="repeatPasswordArea">
              <view class="progressBar"></view>
            </view>
            <view class="nextButton">NEXT</view>
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

