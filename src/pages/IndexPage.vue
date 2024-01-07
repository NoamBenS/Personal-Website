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
    directory: '/me/catsleep',
  },
  {
    image: 'catsleep.jpeg',
    color: 'redgreen',
    label: 'Stock Terminal',
    directory: '/me/catsleep',
  },
  {
    image: 'catsleep.jpeg',
    color: 'orangeblue',
    label: 'Personal Website',
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
