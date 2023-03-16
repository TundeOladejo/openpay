<script setup>
import MainSide from '../components/MainSide.vue' 
import SideBar from '../components/SideBar.vue'
</script>

<template>
  <div class="container is-fullhd dashboard">
    <div class="columns is-desktop">
      <div class="aside column is-narrow">
        <SideBar />
      </div>
      <div class="mainside column is-variable px-5 has-text-weight-semibold">
        <MainSide />
      </div>
    </div>
  </div>
</template>

<style scoped>
.aside {
  border-right: 2px solid #EDF1F2;
}
.mainside {
  font-family: 'Roboto', sans-serif;
  font-weight: 500 !important;
}
</style>
