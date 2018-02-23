<style lang="scss">
.container {
  color: red;
  background-color: red;
  border: 1px red solid;
}



</style>
<template>
  <view class="container">test</view>
  <input type="text">哈哈哈</input>
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
