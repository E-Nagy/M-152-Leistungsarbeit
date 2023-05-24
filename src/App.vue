<script setup>
import { RouterLink, RouterView } from 'vue-router'

</script>

<template>
  <header>
    <nav>
      <ul>
        <li>
          <RouterLink to="/">Noten</RouterLink>
        </li>
        <li>
          <RouterLink to="/profil">Profil</RouterLink>
        </li>
        <li>
          <RouterLink to="/logout">Logout</RouterLink>
        </li>
      </ul>
    </nav>
  </header>

  <RouterView />


</template>

<style lang="scss">
  dialog > div {
    padding-bottom: 20px;
  }
</style>
