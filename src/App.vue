<template>
  <header>
    <UnionLogo
      class="union-logo"
    />
    <nav>
      <router-link to="/">Home</router-link> |
    </nav>
  </header>
  <router-view></router-view>
</template>

<script>
import UnionLogo from '@/components/UnionLogo.vue';

export default {
  name: "UnionCreative",

  components: {
    UnionLogo
  }
}
</script>

<style lang="scss">
  @import '@/assets/sass/main.scss';
</style>
