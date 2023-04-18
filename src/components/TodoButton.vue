  <script setup>
 
  </script>


<template>
  <button >
    <slot>Create</slot>
  </button>
</template>


<style lang="scss" scoped>
 button {
    padding: 8px 16px;
    border: none;
   
    border-bottom-right-radius:1em ;
    border-top-right-radius: 1em;
  }
</style>