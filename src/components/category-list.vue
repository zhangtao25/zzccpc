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

    border: 1px solid #e0e0e0;
    border-left: 0;
    box-shadow: 0 8px 16px rgba(0,0,0,0.18);
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
    <span class="category-list-title">
      <i class="iconfont icon-list" style="font-size: 18px"></i>
      {{$t("category.list.all.product.categories")}}
    </span>
    <div class="category-list-content"
    @mouseleave="closeAllActiveLargeclass">
      <ul class="ul-li_a">
        <li
          v-for="(virtualLargeclass,index) of virtualLargeclasses" :key="index"
          @mousemove="triggerActiveLargeclass(index)"
          :style="{'background-color': activeLargeColor[index],'display':'flex'}">
          <span style="display: block;width: 170px">{{virtualLargeclass}}</span>
          <i class="iconfont icon-right" style="font-size: 18px"></i>
        </li>
      </ul>
      <div>
        <ul
          class="ul-li_a"
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
  import {mapGetters} from 'vuex'
  export default {
    data(){
      return{
        virtualLargeclasses:[
          this.$t("bohea"),this.$t("green.tea"),
          this.$t("white.tea"),this.$t("black.tea"),
          this.$t("oolong"),this.$t("scented.tea"),
          this.$t("yellow.tea"),this.$t("medicinal.tea"),
          this.$t("tea.set"),this.$t("other"),
        ],
        virtualDatas:[],
        activeLargeclass: Array(10).fill(false),
        activeLargeColor:Array(10).fill('rgba(0, 0, 0, 0)')
      }
    },
    mounted(){
      let _this = this
      axios.get(_this.dataReqUrl+'/allTypesOfTea')
      .then(function (response) {
        for (let i=0;i<response.data.length;i++){
          _this.virtualDatas.push({
            "largeclass":response.data[i][_this.langCode+"_largeclass"],
            "smallclass":response.data[i][_this.langCode+"_smallclass"]
          })
        }
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
          if(this.virtualDatas[i]['largeclass'] == this.virtualLargeclasses[0]){
            datashuliang[0]++
          }else if(this.virtualDatas[i]['largeclass'] == this.virtualLargeclasses[1]){
            datashuliang[1]++
          }else if(this.virtualDatas[i]['largeclass'] == this.virtualLargeclasses[2]){
            datashuliang[2]++
          }else if(this.virtualDatas[i]['largeclass'] == this.virtualLargeclasses[3]){
            datashuliang[3]++
          }else if(this.virtualDatas[i]['largeclass'] == this.virtualLargeclasses[4]){
            datashuliang[4]++
          }else if(this.virtualDatas[i]['largeclass'] == this.virtualLargeclasses[5]){
            datashuliang[5]++
          }else if(this.virtualDatas[i]['largeclass'] == this.virtualLargeclasses[6]){
            datashuliang[6]++
          }else if(this.virtualDatas[i]['largeclass'] == this.virtualLargeclasses[7]){
            datashuliang[7]++
          }else if(this.virtualDatas[i]['largeclass'] == this.virtualLargeclasses[8]){
            datashuliang[8]++
          }else if(this.virtualDatas[i]['largeclass'] == this.virtualLargeclasses[9]){
            datashuliang[9]++
          }else{}
        }
        let activeLargeclassWidth = []
        for(let i in datashuliang){
          activeLargeclassWidth.push(Math.ceil(datashuliang[i]/6)*245+'px')
        }
        return activeLargeclassWidth
      },
      ...mapGetters(["langCode"])
    }
  }
</script>
