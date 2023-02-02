<template>
  <header id="main-header">
    <UnionLogo
      class="union-logo" />
    <nav>
      <i class="fa-solid fa-bars"></i>
      <button @click="showContact">Show Contact</button>
    </nav>
  </header>

  <!-- contact component here - should be on every page -->
  <ContactComponent @closeform="this.displayContact = false" :class="{ 'show-form' : displayContact }"/>

  <!-- end contact component-->
  <router-view></router-view>
</template>

<script>
import UnionLogo from '@/components/UnionLogo.vue';
import ContactComponent from '@/components/ContactComponent.vue';

export default {
  name: "UnionCreative",

  data() {
    return {
      displayContact: false
    }    
  },

  methods: {
    showContact() {
      this.displayContact = !this.displayContact;
    }
  },

  components: {
    UnionLogo,
    ContactComponent
  }
}
</script>

<style lang="scss">
  @import '@/assets/sass/main.scss';
</style>
