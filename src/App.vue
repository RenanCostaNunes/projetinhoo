<script setup>
import MovieList from './components/MovieList.vue'
</script>

<template>
<header>
<img class="logo" src="./assets/shrekFera.jpg" alt="Logo do Shrek" />

</header>

  <main class="main-container">
    <TheWelcome />
    <MovieList />
  </main>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
  width: 500px; 
  height: auto; 
}

.main-container {
  display: flex;
  flex-direction: column; 
  justify-content: center;
  align-items: center; 
  min-height: 5%; 
}

@media (min-width: 1024px) {
  header {
    text-align: center;
  }
}
</style>
