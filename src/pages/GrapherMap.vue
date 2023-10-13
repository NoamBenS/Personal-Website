<template>
  <q-page class="main">
    <div>
      <q-btn class="gohome" color="black" label="go back to home" to="/" />
    </div>
    <DataGrapher></DataGrapher>
  </q-page>
</template>

<script setup>
import DataGrapher from 'components/DataGrapher.vue';
</script>
