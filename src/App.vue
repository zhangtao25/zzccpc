<template>
  <router-view></router-view>
</template>
<style>
  @font-face {
    font-family: 'iconfont';  /* project id 803857 */
    src: url('//at.alicdn.com/t/font_803857_os45gx105e.eot');
    src: url('//at.alicdn.com/t/font_803857_os45gx105e.eot?#iefix') format('embedded-opentype'),
    url('//at.alicdn.com/t/font_803857_os45gx105e.woff') format('woff'),
    url('//at.alicdn.com/t/font_803857_os45gx105e.ttf') format('truetype'),
    url('//at.alicdn.com/t/font_803857_os45gx105e.svg#iconfont') format('svg');
  }
  .iconfont {
    font-family:"iconfont" !important;
    font-size:14px;
    font-style:normal;
    -webkit-font-smoothing: antialiased;
    -webkit-text-stroke-width: 0.2px;
    -moz-osx-font-smoothing: grayscale;
  }

  .icon-cart:before{ content: "\e660" }

  .margin{margin: 0 auto;width: 1190px}
  .ul-li_a>li{color: #b0b0b0}
  .ul-li_a>li:hover{cursor: pointer;color: #e64318}
  input{display: block;border: none}
</style>
