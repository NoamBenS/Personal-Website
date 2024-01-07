<template>
  <div class="main" style="display: flex; align-items: center">
    <q-btn color="black" label="Cat Pics" to="/me/catsleep" />
    <ButtonLink
      class="linkbox"
      v-for="button in linkBlocks"
      :key="button.link"
      v-bind="button"
    />
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
import ButtonLink from 'components/ButtonLink.vue';
import { defineComponent } from 'vue';

const blocks = [
  {
    image: 'icons/linkedin100.png',
    color: 'yellowpurple',
    label: 'LinkedIn',
    directory: '/me/catsleep',
  },
  {
    image: 'icons/github100.png',
    color: 'redgreen',
    label: 'Github',
    directory: '/me/catsleep',
  },
  {
    image: 'catsleep.jpeg',
    color: 'yellowpurple',
    label: 'Personal Website',
    directory: '/me/catsleep',
  },
  {
    image: 'catsleep.jpeg',
    color: 'yellowpurple',
    label: 'Stock Terminal',
    directory: '/me/catsleep',
  },
  {
    image: 'catsleep.jpeg',
    color: 'orangeblue',
    label: 'Personal Website',
    directory: '/me/catsleep',
  },
  {
    image: 'catsleep.jpeg',
    color: 'orangeblue',
    label: 'Stock Terminal',
    directory: '/me/catsleep',
  },
];

const links = [
  {
    image: 'icons/linkedin100.png',
    color: 'yellowpurple',
    label: 'LinkedIn',
    link: 'https://github.com/NoamBenS',
  },
  {
    image: 'icons/github100.png',
    color: 'redgreen',
    label: 'Github',
    link: 'https://www.linkedin.com/in/noam-ben-simon/',
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
      linkBlocks: links,
    };
  },
});
</script>

<style></style>
