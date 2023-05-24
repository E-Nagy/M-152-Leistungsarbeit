<script setup>
import { RouterLink, RouterView } from 'vue-router'

function logout() {
  window.location.href = 'https://google.com'
}
</script>

<template>
  <header>
    <nav>
      <ul>
        <li>
          <RouterLink to="/">Noten</RouterLink>
        </li>
        <li>
          <RouterLink to="/about">Profil</RouterLink>
        </li>
        <li>
          <a href="#">Logout</a>
        </li>
      </ul>
    </nav>
  </header>

  <RouterView />

  <dialog ref="dialogElement">
    <div>
      Möchten Sie sich wirklich abmelden?
    </div>

    <button @click="logout">Ja</button>
    <button value="Nein">Nein</button>
  </dialog>
</template>

<style lang="scss">
  dialog > div {
    padding-bottom: 20px;
  }
</style>
