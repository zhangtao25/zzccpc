<style>
  .classified-display-cabinet{background-color: #f5f5f5}
  .classified-display-cabinet>.margin>.box-hd{display: flex;justify-content: space-between}
  .classified-display-cabinet>.margin>.box-hd>.nav{display: flex;margin-top: 20px;cursor: pointer}
  .classified-display-cabinet>.margin>.box-hd>.nav>li{
    height: 26px;
    margin-left: 30px;
    color: #000;
    border-bottom: 2px solid rgba(0,0,0,0);
    transition-property: border-color;
    transition-duration: 0.5s;
    transition-timing-function: ease;
    transition-delay: 0s;
    }
  .classified-display-cabinet>.margin>.box-hd>.nav>li:hover{
    margin-left: 30px;
    color: #ff6700;
    border-bottom: 2px solid #ff6700;
  }
  .classified-display-cabinet>.margin>.box-hd>h2{
    font-size: 22px;
    font-weight: 200;
    line-height: 58px;
    color: #333;
  }

  .classified-display-cabinet>.margin>.box-bd{display: flex}

  .classified-display-cabinet>.margin>.box-bd>.box-bd-l>li{
    width: 234px;height: 300px;
    background-color: #3a8ee6;
    margin-right: 14px;
    background-image: url("https://i1.mifile.cn/a4/xmad_15232433421155_vCzhJ.jpg");
    background-size: cover;

    transition-property: all;
    transition-duration: 0.2s;
    transition-timing-function: linear;
    transition-delay: 0s;
  }
  .classified-display-cabinet>.margin>.box-bd>.box-bd-l>li:nth-child(1){margin-bottom: 14px;}
  .classified-display-cabinet>.margin>.box-bd>.box-bd-l>li:hover{
    transform: translateY(-5px);
    box-shadow: 0 15px 30px rgba(0,0,0,0.1);
    cursor: pointer;
  }

  .classified-display-cabinet>.margin>.box-bd>.box-bd-r{
    height: 614px;
    display: flex;
    flex-flow: wrap;
    justify-content: space-between;
    align-content: space-between;
  }
  .classified-display-cabinet>.margin>.box-bd>.box-bd-r>li{
    width: 234px;height: 300px;
    background-color: #fff;
    display: flex;
    flex-direction: column;
    align-items: center;

    transition-property: all;
    transition-duration: 0.2s;
    transition-timing-function: linear;
    transition-delay: 0s;
  }
  .classified-display-cabinet>.margin>.box-bd>.box-bd-r>li:hover{
    transform: translateY(-5px);
    box-shadow: 0 15px 30px rgba(0,0,0,0.1);
    cursor: pointer;
  }
  .classified-display-cabinet>.margin>.box-bd>.box-bd-r>li>.review-wrapper>div{
    transform: translateY(32px);
    transition-property: all;
    transition-duration: 0.2s;
    transition-timing-function: linear;
    transition-delay: 0s;
  }
  .classified-display-cabinet>.margin>.box-bd>.box-bd-r>li:hover>.review-wrapper>div{transform: translateY(-35px)}

  .classified-display-cabinet>.margin>.box-bd>.box-bd-r>li>.saleoff{width: 64px;height: 20px;background-color: #3a8ee6}
  .classified-display-cabinet>.margin>.box-bd>.box-bd-r>li>.figure{width: 150px;height: 150px;background-color: #8c939d}
</style>
<template>
  <div class="classified-display-cabinet">
    <div class="margin">
      <!--box-hd-->
      <div class="box-hd">
        <h2 style="line-height: 58px">家电</h2>
        <ul class="nav">
          <li>热门</li>
          <li>黄山毛峰</li>
          <li>祁门红茶</li>
          <li>铁观音</li>
        </ul>
      </div>
      <!--box-bd-->
      <div class="box-bd">
        <ul class="box-bd-l">
          <li></li>
          <li></li>
        </ul>
        <ul class="box-bd-r">
          <li v-for="(item,index) of msg" style="overflow: hidden">
            <div class="saleoff" style="text-align: center;color: white;margin-bottom: 16px">减300元</div>
            <div
              class="figure"
              style="background-image: url('https://i1.mifile.cn/a1/pms_1524883847.49276938!220x220.jpg');background-size: cover;margin-bottom: 10px">

            </div>
            <p>小米电视4A 43寸青春版</p>
            <div class="desc" style="font-size: 12px;color: #b0b0b0;margin-bottom: 14px">全高清屏/人工智能语音</div>
            <p>
              <span style="color: #ff6700">1399元</span>
              <span style="color: #b0b0b0">1699元</span>
            </p>

            <div
              class="review-wrapper"
              style="height: 0;width: 234px">
              <div style="width: 174px;height: 59px;background-color: #ff6700;display: flex;flex-direction: column;padding: 8px 30px 8px 30px;">
                <span class="review" style="color: #fff;font-size: 12px">我不是来评价电视的我是来拉仇恨的，38.46的电视请...</span>
                <span class="author" style="color: rgba(255,255,255,0.6);font-size: 12px"> 来自于 果然发烧 的评价 </span>
              </div>
            </div>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>
<script>
  export default {
    data(){
      return {
        msg:Array(8)
      }
    },
    props:["teaDetails"],
    mounted(){
      console.log(this.teaDetails)
    }
  }
</script>
