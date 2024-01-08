<template>
  <div class="main" style="display: flex; align-items: center">
    <container class="introduction">
      <ButtonLink
        class="linkbox"
        v-for="button in linkBlocks"
        :key="button.link"
        v-bind="button"
      />
    </container>
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
    image: 'catsleep.jpeg',
    color: 'yellowpurple',
    label: 'Personal Website',
    text: 'hello, world!',
    directory: '/me/catsleep',
  },
  {
    image: 'catsleep.jpeg',
    color: 'redgreen',
    label: 'Stock Terminal',
    text: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.',
    directory: '/me/catsleep',
  },
  {
    image: 'catsleep.jpeg',
    color: 'orangeblue',
    label: 'Personal Website',
    text: 'hello, world!',
    directory: '/me/catsleep',
  },
];

const links = [
  {
    image: 'icons/linkedin100.png',
    color: '#B0CBA9',
    label: 'LinkedIn',
    link: 'https://www.linkedin.com/in/noam-ben-simon/',
  },
  {
    image: 'icons/github100.png',
    color: '#B0CBA9',
    label: 'Github',
    link: 'https://github.com/NoamBenS',
  },
];

export default defineComponent({
  name: 'MainLayout',

  components: {
    InformationBlock,
    ButtonLink,
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
