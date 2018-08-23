<style>
  .category-list{height: 60px;position: relative;}
  .category-list>.category-list-title{
    width: 234px;height: 60px;
    font-size:16px;
    line-height:60px;
    display: block;
    /* border: 1px solid salmon */
    }
    .category-list>.category-list-content{display: flex;font-size: 16px;position: absolute;top: 60px;left: 0;}
    .category-list>.category-list-content>ul{background-color: rgba(0, 0, 0, 0.6);padding: 20px 0 20px 0;}
    .category-list>.category-list-content>ul>li{width: 204px;line-height: 42px;padding-left: 30px;color: #fff}
    .category-list>.category-list-content>ul>li:hover{background-color: #ff6700}

    .category-list>.category-list-content>div{height: 460px;background-color: #fff;}
    /* .category-list>.category-list-content>div>ul{border: 1px solid crimson} */
    .category-list>.category-list-content>div>ul{
      width: 992px;
      border-right: 1px solid saddlebrown;
      height: 460px;
      display: flex;
      flex-wrap:wrap;
      flex-direction: column;
      align-content: flex-start
      }
    .category-list>.category-list-content>div>ul>li{
      width: 245px;
      height: 76px;
      display: flex;
      align-items: center;
      padding-left: 20px;
      font-size: 14px;
      color: #333
      }
    .category-list>.category-list-content>div>ul>li>img{width: 40px;height: 40px;margin-right: 12px}
</style>
<template>
  <div class="category-list margin">
    <span class="category-list-title iconfont icon-list">全部商品分类</span>
    <div class="category-list-content">
      <ul class="ul-li_a">
        <li v-for="(item,index) of virtualLargeclass" :key="index" 
          @mousemove="triggerActiveLargeclass(index)"
          @mouseleave="closeAllActiveLargeclass">
          {{item}}
        </li>
      </ul>
      <div>
        <ul class="ul-li_a" 
          v-for="(item,index) of virtualLargeclass" 
          :key="index" v-show="activeLargeclass[index]"
          @mousemove="fn(index)">
          <li  v-for="(item_li,index) of virtualData" :key="index" v-if="item==item_li.largeclass">
            <img src="https://i1.mifile.cn/f/i/g/2015/cn-index/m8-80.png?width=80&height=80" alt="">
            <span>{{item_li.smallclass}}</span>
          </li>
          
        </ul>
      </div>
    </div>
  </div>
</template>
<script>
  export default {
    data(){
      return{
        virtualLargeclass:['红茶','绿茶','白茶','黑茶','乌龙茶'],
        virtualData:[
          {'largeclass': '红茶','smallclass':'红茶0'},
          {'largeclass': '红茶','smallclass':'红茶1'},
          {'largeclass': '红茶','smallclass':'红茶2'},
          {'largeclass': '红茶','smallclass':'红茶3'},
          {'largeclass': '红茶','smallclass':'红茶4'},
          {'largeclass': '红茶','smallclass':'红茶5'},
          {'largeclass': '红茶','smallclass':'红茶6'},
          {'largeclass': '红茶','smallclass':'红茶7'},
          {'largeclass': '红茶','smallclass':'红茶8'},
          {'largeclass': '红茶','smallclass':'红茶9'},

          {'largeclass': '红茶','smallclass':'红茶5'},
          {'largeclass': '红茶','smallclass':'红茶6'},
          {'largeclass': '红茶','smallclass':'红茶7'},
          {'largeclass': '红茶','smallclass':'红茶8'},
          {'largeclass': '红茶','smallclass':'红茶9'},

          {'largeclass': '绿茶','smallclass':'绿茶0'},
          {'largeclass': '绿茶','smallclass':'绿茶1'},
          {'largeclass': '绿茶','smallclass':'绿茶2'},
          {'largeclass': '绿茶','smallclass':'绿茶3'},
          {'largeclass': '绿茶','smallclass':'绿茶4'},
          {'largeclass': '绿茶','smallclass':'绿茶5'},
          {'largeclass': '绿茶','smallclass':'绿茶6'},
          {'largeclass': '绿茶','smallclass':'绿茶7'},
          {'largeclass': '绿茶','smallclass':'绿茶8'},
          {'largeclass': '绿茶','smallclass':'绿茶9'},

          {'largeclass': '白茶','smallclass':'白茶0'},
          {'largeclass': '白茶','smallclass':'白茶1'},
          {'largeclass': '白茶','smallclass':'白茶2'},
          {'largeclass': '白茶','smallclass':'白茶3'},
          {'largeclass': '白茶','smallclass':'白茶4'},
          {'largeclass': '白茶','smallclass':'白茶5'},
          {'largeclass': '白茶','smallclass':'白茶6'},
          {'largeclass': '白茶','smallclass':'白茶7'},
          {'largeclass': '白茶','smallclass':'白茶8'},
          {'largeclass': '白茶','smallclass':'白茶9'},

          {'largeclass': '黑茶','smallclass':'黑茶0'},
          {'largeclass': '黑茶','smallclass':'黑茶1'},
          {'largeclass': '黑茶','smallclass':'黑茶2'},
          {'largeclass': '黑茶','smallclass':'黑茶3'},
          {'largeclass': '黑茶','smallclass':'黑茶4'},
          {'largeclass': '黑茶','smallclass':'黑茶5'},
          {'largeclass': '黑茶','smallclass':'黑茶6'},
          {'largeclass': '黑茶','smallclass':'黑茶7'},
          {'largeclass': '黑茶','smallclass':'黑茶8'},
          {'largeclass': '黑茶','smallclass':'黑茶9'},

          {'largeclass': '乌龙茶','smallclass':'乌龙茶0'},
          {'largeclass': '乌龙茶','smallclass':'乌龙茶1'},
          {'largeclass': '乌龙茶','smallclass':'乌龙茶2'},
          {'largeclass': '乌龙茶','smallclass':'乌龙茶3'},
          {'largeclass': '乌龙茶','smallclass':'乌龙茶4'},
          {'largeclass': '乌龙茶','smallclass':'乌龙茶5'},
          {'largeclass': '乌龙茶','smallclass':'乌龙茶6'},
          {'largeclass': '乌龙茶','smallclass':'乌龙茶7'},
          {'largeclass': '乌龙茶','smallclass':'乌龙茶8'},
          {'largeclass': '乌龙茶','smallclass':'乌龙茶9'},
        ],
        activeLargeclass:[false,false,false,false,false]
      }
    },
    methods:{
      triggerActiveLargeclass(index){
        this.activeLargeclass = [false,false,false,false,false];
        this.activeLargeclass[index] = true;
      },
      closeAllActiveLargeclass(){
        setTimeout(()=>{
          this.activeLargeclass = [false,false,false,false,false];
        },1000)
        
      },
      fn(index){
        // setTimeout


        setTimeout(()=>{
          this.activeLargeclass[index] = true;
          console.log(1111)
        },1100)
      }
    }
  }
</script>
