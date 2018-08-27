<style>
  .category-list{height: 60px;position: relative;z-index: 100}
  .category-list>.category-list-title{
    width: 234px;height: 60px;
    font-size:16px;
    line-height:60px;
    display: block;
  }
  .category-list>.category-list-content{display: flex;font-size: 16px;position: absolute;top: 60px;left: 0;}
  .category-list>.category-list-content>ul{background-color: rgba(0, 0, 0, 0.6);padding: 20px 0 20px 0;}
  .category-list>.category-list-content>ul>li{width: 204px;line-height: 42px;padding-left: 30px;color: #fff}
  .category-list>.category-list-content>div{height: 460px;}
  .category-list>.category-list-content>div>ul{
    border-right: 1px solid saddlebrown;
    height: 460px;
    display: flex;
    flex-wrap:wrap;
    flex-direction: column;
    align-content: flex-start;
    background-color: #fff
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
  .category-list>.category-list-content>div>ul>li:hover{color: #ff6700}
  .category-list>.category-list-content>div>ul>li>img{width: 40px;height: 40px;margin-right: 12px}
</style>
<template>
  <div class="category-list margin">
    <span class="category-list-title iconfont icon-list">全部商品分类</span>
    <div class="category-list-content"
    @mouseleave="closeAllActiveLargeclass">
      <ul class="ul-li_a">
        <li v-for="(virtualLargeclass,index) of virtualLargeclasses" :key="index"
          @mousemove="triggerActiveLargeclass(index)"
          :style="{'background-color': activeLargeColor[index]}">
          {{virtualLargeclass}}
        </li>
      </ul>
      <div>
        <ul class="ul-li_a"
          :style="{'width':activeLargeclassWidth[index]}"
          v-for="(virtualLargeclass,index) of virtualLargeclasses"
          :key="index"
          v-show="activeLargeclass[index]"
          @mouseleave="closeAllActiveLargeclass">
          <li
            v-for="(virtualData,index) of virtualDatas"
            :key="index"
            v-if="virtualLargeclass==virtualData.largeclass">
            <img src="https://i1.mifile.cn/f/i/g/2015/cn-index/m8-80.png?width=80&height=80" alt="">
            <span>{{virtualData.smallclass}}</span>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>
<script>
  import axios from 'axios'
  export default {
    data(){
      return{
        virtualLargeclasses:['红茶','绿茶','白茶','黑茶','乌龙茶','花茶','黄茶','药茶','茶具','其它'],
        virtualDatas:[],
        activeLargeclass: Array(10).fill(false),
        activeLargeColor:Array(10).fill('rgba(0, 0, 0, 0)')
      }
    },
    mounted(){
      let _this = this
      axios.get('http://localhost:3002/test')
      .then(function (response) {
        _this.virtualDatas = response.data
      })
      .catch(function (error) {
        console.log(error);
      });
    },
    methods:{
      triggerActiveLargeclass(index){
        this.activeLargeclass = Array(10).fill(false)
        this.activeLargeColor = Array(10).fill('rgba(0, 0, 0, 0)');
        this.activeLargeclass[index] = true;
        this.activeLargeColor[index] = '#ff6700'
      },
      closeAllActiveLargeclass(){
        this.activeLargeclass = Array(10).fill(false)
        this.activeLargeColor = Array(10).fill('rgba(0, 0, 0, 0)');
      }
    },
    computed:{
      activeLargeclassWidth(){
        let datashuliang = Array(10).fill(0)
        for(let i in this.virtualDatas){
          if(this.virtualDatas[i]['largeclass'] == "红茶"){
            datashuliang[0]++
          }else if(this.virtualDatas[i]['largeclass'] == "绿茶"){
            datashuliang[1]++
          }else if(this.virtualDatas[i]['largeclass'] == "白茶"){
            datashuliang[2]++
          }else if(this.virtualDatas[i]['largeclass'] == "黑茶"){
            datashuliang[3]++
          }else if(this.virtualDatas[i]['largeclass'] == "乌龙茶"){
            datashuliang[4]++
          }else if(this.virtualDatas[i]['largeclass'] == "花茶"){
            datashuliang[5]++
          }else if(this.virtualDatas[i]['largeclass'] == "黄茶"){
            datashuliang[6]++
          }else if(this.virtualDatas[i]['largeclass'] == "药茶"){
            datashuliang[7]++
          }else if(this.virtualDatas[i]['largeclass'] == "茶具"){
            datashuliang[8]++
          }else if(this.virtualDatas[i]['largeclass'] == "其它"){
            datashuliang[9]++
          }else{}
        }
        let activeLargeclassWidth = []
        for(let i in datashuliang){
          activeLargeclassWidth.push(Math.ceil(datashuliang[i]/6)*245+'px')
        }
        return activeLargeclassWidth
      }
    }
  }
</script>
