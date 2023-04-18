  <script setup>
 
  </script>


<template>
  <button >
    <slot>Create</slot>
  </button>
</template>


<style lang="scss" scoped>
 button {
  background-color: #010101;
  color:#fff;
    padding: 8px 16px;
    border: none;
    width:80%;
    margin:auto;
   margin-top:2em;
    border-radius:1em ;
    
    
  }
button:hover {
  transform: scale(.95);
}
button:active {
  background-color:#2eaae4 ;
  animation-duration: 2000ms ease-in-out;
}
</style>