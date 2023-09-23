
<template>
  <div>
    <Suspense>
      <template #default>
        <profileCard/>
      </template>
      <template #fallback>
        <profileCrdSkeliton/>
      </template>
    </Suspense>
   
  </div>

</template>

<script setup>
import profileCard from './components/icons/profileCard.vue';
import profileCrdSkeliton from './components/icons/profileCardSkeliton.vue';
</script>

<style scoped>
html,
body {
  background-color: #eee;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
</style>