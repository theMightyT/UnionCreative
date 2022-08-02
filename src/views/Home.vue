<template>
   <WorkComponent v-for="item in work" :key="item.id" :data="item"/>
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
  .work {
    width: 100%;
    height: 100vh;
    
    background-position: center;
  }
</style>
 