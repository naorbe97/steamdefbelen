<template>
  <div>
    <NavBar />
    <NuxtPage />
    <Footer />
  </div>
</template>

<style lang="postcss">
  *{
    box-sizing: border-box; 
    font-family: 'DM Mono', monospace;
    font-family: Roboto;
  }
  h1{
    font-size: 2em;
  }
  .containert{
    @apply p-8;
  } 
</style>