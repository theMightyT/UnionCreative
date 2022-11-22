<template>
  <section class="wrapper">
    <WorkComponent v-for="item in work" :key="item.id" :data="item" />
  </section>
</template>

<script>
import data from '@/store/data.js';
import WorkComponent from '@/components/WorkComponent.vue';

export default {
  name: 'HomeView',

  data() {
    return {
      work: data
    }
  },

  components: {
    WorkComponent   
  }
}
</script>

<style lang="scss">
  .wrapper { padding-top: 52px; }
  .work {
    width: 100vw;
    height: 100vh;
    
    background-position: center;
  }
</style>
 