<template>
  <q-page class="main">
    <q-img src="catsleep.jpeg" style="height: 500px; width: 400px" />
    <div>
      <q-btn class="gohome" label="go back to home" to="/" />
    </div>
    <InformationBlock
      v-for="block in informationBlocks"
      :key="block.directory"
      v-bind="block"
    />
  </q-page>
</template>

<script lang="ts">
import InformationBlock from 'components/InformationBlock.vue';
import { defineComponent } from 'vue';

const blocks = [
  {
    image: 'catsleep.jpeg',
    color: 'orange',
    label: 'Test1',
    directory: '/',
  },
  {
    image: 'catsleep.jpeg',
    color: 'green',
    label: 'Boy',
    directory: '/',
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
