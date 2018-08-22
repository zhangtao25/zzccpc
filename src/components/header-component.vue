<style>
  header{background-color: #333}
  header>.margin{display: flex;line-height: 40px}
  header>.margin>.l>ul{height: 40px;display: flex;margin-right: 200px}
  header>.margin>.l>ul>li{margin-right: 32px}
  header>.margin>.r>ul{height: 40px;display: flex}
  header>.margin>.r>ul>li{margin-right: 32px}
  header>.margin>.cart-btn{height: 40px;width: 120px;display: block;display: flex;background-color: #ff3600;overflow: hidden}
  header>.margin>.cart-btn>.img-wrap{transform: translateY(0);transition: .2s}
  header>.margin>.cart-btn:hover>.img-wrap{transform: translateY(-30px)}
  header>.margin>.cart-btn:hover{background-color:#ccc}
  header>.margin>.cart-btn:hover>input{background-color: #ccc;color: #ff3600}
  header>.margin>.cart-btn>.img-wrap>img{display: block;width: 20px;margin: 10px}
  header>.margin>.cart-btn>input{background-color: #ff3600;font-size: 16px;color: #fff;}

</style>
<template>
  <header>
    <div class="margin">
      <div class="l">
        <ul class="ul-li_a">
          <li>枝枝茶城首页</li>
          <li>枝枝茶城手机版</li>
        </ul>
      </div>
      <div class="r">
        <ul  class="ul-li_a">
          <li>登录</li>
          <li>注册</li>
          <li>我的订单</li>
          <li>帮助中心</li>
          <li>关于枝枝</li>
          <li>4000-000-000</li>
        </ul>
      </div>
      <div class="cart-btn">
        <div class="img-wrap">
          <img src="./../assets/images/cart2.png" alt="">
          <img src="./../assets/images/cart1.png" alt="">
        </div>
        <input type="button" value="购物车">
      </div>
    </div>
  </header>
</template>
