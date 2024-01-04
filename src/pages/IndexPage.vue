<template>
  <div class="main" style="display: flex; align-items: center">
    <h3>Home</h3>
    <q-btn color="black" label="Cat Pics" to="/me/catsleep" />
    <InformationBlock
      class="box"
      v-for="block in informationBlocks"
      :key="block.directory"
      v-bind="block"
    />
  </div>
</template>

<script>
import InformationBlock from 'components/InformationBlock.vue';
import { defineComponent } from 'vue';

const blocks = [
  {
    image: 'catsleep.jpeg',
    color: 'orange',
    label: 'Stock Terminal',
    directory: '/me/catsleep',
  },
  {
    image: 'catsleep.jpeg',
    color: 'green',
    label: 'Personal Website',
    directory: '/me/catsleep',
  },
];

export default defineComponent({
  name: 'MainLayout',

  components: {
    InformationBlock,
  },

  setup() {
    return {
      informationBlocks: blocks,
    };
  },
});
</script>

<style></style>
