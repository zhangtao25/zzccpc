<template>
  <div id="home">
    <header-component></header-component>
    <logo-and-search-component></logo-and-search-component>
  </div>
</template>
<script>
  import HeaderComponent from "./../components/header-component"
  import LogoAndSearchComponent from "./../components/logo-and-search-component"
  export default {
    components: {
      'header-component': HeaderComponent,
      'logo-and-search-component': LogoAndSearchComponent
    }
  }
</script>
