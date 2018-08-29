<template>
  <div id="home">
    <header-component></header-component>
    <logo-and-search-component></logo-and-search-component>
    <category-list></category-list>
    <banner-component></banner-component>
    <classified-display-cabinet :tea-details="testTeaDetails"></classified-display-cabinet>
  </div>
</template>
<script>
  import HeaderComponent from "./../components/header-component"
  import LogoAndSearchComponent from "./../components/logo-and-search-component"
  import CategoryList from "./../components/category-list"
  import BannerComponent from "./../components/banner-component"
  import ClassifiedDisplayCabinet from "./../components/classified-display-cabinet"

  import axios from 'axios'

  export default {
    components: {
      'header-component': HeaderComponent,
      'logo-and-search-component': LogoAndSearchComponent,
      'category-list': CategoryList,
      'banner-component': BannerComponent,
      'classified-display-cabinet': ClassifiedDisplayCabinet
    },
    data(){
      return {
        testTeaDetails:"TEST"
      }
    },
    mounted(){
      let _this = this;
      axios.get(_this.dataReqUrl+"/allTeaDetails")
        .then(function (response) {
          console.log(response.data,"csacsa")
        })
        .catch(function (error) {
          console.log(error);
        });
    }
  }
</script>
