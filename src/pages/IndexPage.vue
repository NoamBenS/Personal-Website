<template>
  <div class="main" style="display: flex; align-items: center">
    <container class="introduction">
      <q-img
        :src="'/images/me.png'"
        style="
          max-height: 400px;
          max-width: 200px;
          display: flex;
          border-radius: 10px;
        "
      />
      <div style="align-items: column">
        <q-item class="textbox">
          Hey! I'm Noam, an aspiring Computer Science and Music Theory Student
          at Yeshiva University. <br />
          While in school, I have worked hard to grow and develop my skillset
          and knowledge in the field, including projects such as this website
          and my ongoing project with my partner in creating a Stock Terminal
          API. <br />
        </q-item>
        <div class="links">
          <ButtonLink
            class="linkbox"
            v-for="button in linkBlocks"
            :key="button.link"
            v-bind="button"
          />
        </div>
      </div>
    </container>

    <h class="header"> Projects </h>

    <InformationBlock
      class="box"
      v-for="block in informationBlocks"
      :key="block.directory"
      v-bind="block"
    />

    <h class="header"> Skills </h>

    <h class="header"> Extras </h>
    <InformationBlock
      class="chaosbox"
      :image="'/images/chaos.png'"
      :color="'orangeblue'"
      :label="'Creativity Corner'"
      :text="'Get to know me beyond what I do. Fair warning: The UI is really bad. But that\'s on purpose :)'"
      :directory="'/me/catsleep'"
    ></InformationBlock>
  </div>
</template>

<script>
import InformationBlock from 'components/InformationBlock.vue';
import ButtonLink from 'components/ButtonLink.vue';
import { defineComponent } from 'vue';

const blocks = [
  {
    image: '/images/stockterminal.png',
    color: 'yellowpurple',
    label: 'Stock Terminal',
    text: 'Stock Terminal is a Java-based CLI that uses API calls to receive current, relevant, and customizable data on requested tickers. With customizability and professional use in mind, the project is built around user freedom and functionality. My partner and I collaborated and succeeded to develop Stock Terminal as a working program within a week of work.',
    directory: '/me/catsleep',
  },
  {
    image: '/images/catsleep.jpeg',
    color: 'redgreen',
    label: 'Personal Website',
    text: 'This site is a great representation of my joy in programming and turning code into something functional and pleasing. This website also serves as a reflection of my dedication and passion in the field away from the classroom. As a personal project, I had the freedom to choose exactly how I wanted it to look and feel, which served as an incredibly enjoyable and fulfilling endeavor.',
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
