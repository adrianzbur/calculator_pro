<template>

    <div class="button" @click="$emit('buttonWasClicked', button)">
        {{ button.value }}
    </div>



</template>
  
  <script setup>

  defineProps(['button'])

  </script>


  <style>


</style>