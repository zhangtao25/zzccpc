<template>
  <div id="home">
    <header-component></header-component>
    <logo-and-search-component></logo-and-search-component>
    <category-list></category-list>
    <banner-component></banner-component>
  </div>
</template>
<script>
  import HeaderComponent from "./../components/header-component"
  import LogoAndSearchComponent from "./../components/logo-and-search-component"
  import CategoryList from "./../components/category-list"
  import BannerComponent from "./../components/banner-component"
  export default {
    components: {
      'header-component': HeaderComponent,
      'logo-and-search-component': LogoAndSearchComponent,
      'category-list': CategoryList,
      'banner-component': BannerComponent
    }
  }
</script>
