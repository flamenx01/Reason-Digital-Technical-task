<template>
  <the-header />
  <router-view></router-view>
  <the-footer />
</template>

<script setup>
import theHeader from '@/components/common/TheHeader.vue';
import theFooter from '@/components/common/TheFooter.vue';
</script>

<style lang="scss">
  @import '@/assets/css/main.scss';
</style>