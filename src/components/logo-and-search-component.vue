<style>
  .logo-and-search-component{display: flex}
  .logo-and-search-component>.margin>.search>form{display: flex}
  .logo-and-search-component>.margin>.search>form>input:nth-child(1){
    width: 488px;height: 36px;
    border: 1px solid #e0e0e0;
    text-indent: 12px;
  }
  .logo-and-search-component>.margin>.search>form>input:nth-child(2){
    background-image: url("./../assets/images/icon-search.png");
    width: 56px;height: 38px;
    background-repeat: no-repeat;
    background-position: center;
    border: 1px solid #e0e0e0;
    border-left: none;
    background-color: #fff
  }
  .logo-and-search-component>.margin>.search>form>input:nth-child(1).focus{border: 1px solid #ff3600;}
  .logo-and-search-component>.margin>.search>form>input:nth-child(2).focus1{border: 1px solid #ff3600;border-left: none}
  .logo-and-search-component>.margin>.search>form>input:nth-child(2).focus-btn{background-color: #ff3600;background-image: url("./../assets/images/icon-search-s.png");}

</style>
<template>
  <div class="logo-and-search-component">
    <div class="margin">
      <img src="./../assets/images/logo.gif" alt="" class="logo">
      <div class="search">
        <form action="">
          <input type="text" @blur="txtBlur()" @focus="txtFocus()" :class="classObject">
          <input type="button"  @mouseover="btnMouseover()" @mouseleave="btnMouseleave()" :class="classObject1">
        </form>
      </div>
      <div></div>
    </div>
  </div>
</template>

<script>
  export default {
    data(){
      return{
        classObject: {
          'focus': true,
        },
        classObject1: {
          'focus1': true,
          'focus-btn': true
        }
      }
    },
    methods:{
      txtBlur(){
        this.classObject.focus=false;
      },
      txtFocus(){
        this.classObject.focus=true;
      },
      btnMouseleave(){
        this.classObject1.focus1=false;
      },
      btnMouseover(){
        this.classObject1.focus1=true;
      }
    }
  }
</script>
