<template>
  <nav class="navbar is-danger" role="navigation" aria-label="main navigation">
    <div class="container is-max-desktop px-2">
      <div class="navbar-brand">
        <div class="navbar-item is-size-4 is-family-monospace is-black">
          NOTEBOOKIFY
        </div>

        <a
         @click.prevent="showMobileNavBar = !showMobileNavBar"
          role="button"
          class="navbar-burger"
          :class="{'is-active': showMobileNavBar}"
          aria-label="menu"
          aria-expanded="false"
          data-target="navbarBasicExample"
        >
          <span aria-hidden="true"></span>
          <span aria-hidden="true"></span>
          <span aria-hidden="true"></span>
        </a>
      </div>
      
      <div id="navbarBasicExample" class="navbar-menu" :class="{'is-active': showMobileNavBar}">
        <div class="navbar-end">
          <RouterLink to="/" class="navbar-item"> Notes </RouterLink>
          <RouterLink to="/stats" class="navbar-item"> Stats </RouterLink>
        </div>
      </div>
    </div>
  </nav>
</template>

<script setup>

import { ref } from "vue";

/** Mobile Device NavBar */
const showMobileNavBar = ref(false);

</script>

<style>
@media screen and (max-width: 1023px) {
  .navbar-menu {
    position: absolute;
    left: 0;
    width: 100%;
  }
}
</style>