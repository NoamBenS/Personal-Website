<template>
  <div class="main" style="display: flex">
    <container class="introduction">
      <q-img
        :src="'/images/me.jpg'"
        style="
          min-width: 252px;
          max-width: 200px;
          display: flex;
          border-radius: 10px;
          margin: 10px;
          padding: 10px;
        "
      />
      <div style="align-items: column; flex-wrap: wrap">
        <q-item class="introtextbox">
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
      v-for="block in blocks"
      :key="block.label"
      v-bind="block"
    />

    <h class="header"> Skills </h>
    <div class="skills">
      <SkillsBox
        class="skillsbox"
        v-for="skill in skills"
        :key="skill.label"
        v-bind="skill"
      />
    </div>
  </div>
</template>

<script>
import InformationBlock from 'components/InformationBlock.vue';
import ButtonLink from 'components/ButtonLink.vue';
import SkillsBox from 'components/SkillsBox.vue';
import { defineComponent } from 'vue';

const blocks = [
  {
    image: '/images/stockterminal.png',
    color: 'yellowpurple',
    label: 'Stock Terminal',
    text: 'Stock Terminal is a Java-based CLI that uses API calls to receive current, relevant, and customizable data on requested tickers. With customizability and professional use in mind, the project is built around user freedom and functionality. My partner and I collaborated and succeeded to develop Stock Terminal as a working program within a week of work.',
  },
  {
    image: '/images/websiteimage.png',
    color: 'redgreen',
    label: 'Personal Website',
    text: 'This site is a great representation of my joy in programming and turning code into something functional and pleasing. This website also serves as a reflection of my dedication and passion in the field away from the classroom. As a personal project, I had the freedom to choose exactly how I wanted it to look and feel, which served as an incredibly enjoyable and fulfilling endeavor.',
  },
];

const links = [
  {
    image: 'icons/linkedin100.png',
    color: '#FFFF99',
    label: 'LinkedIn',
    link: 'https://www.linkedin.com/in/noam-ben-simon/',
  },
  {
    image: 'icons/github100.png',
    color: '#C8A2C8',
    label: 'Github',
    link: 'https://github.com/NoamBenS',
  },
];

const skills = [
  {
    label: 'Languages',
    icons: ['Java', 'Python', 'C', 'HTML', 'CSS', 'JavaScript', 'TypeScript'],
    iconImages: [
      '/icons/techicons/java.png',
      '/icons/techicons/python.png',
      '/icons/techicons/c.png',
      '/icons/techicons/html.png',
      '/icons/techicons/css.png',
      '/icons/techicons/javascript.png',
      '/icons/techicons/typescript.png',
    ],
    background: 'white',
  },
  {
    label: 'Frameworks',
    icons: ['Vue', 'Quasar', 'Next.js', 'Wordpress'],
    iconImages: [
      '/icons/techicons/vue.png',
      '/icons/techicons/quasar.png',
      '/icons/techicons/next.png',
      '/icons/techicons/wordpress.png',
    ],
    background: 'white',
  },
  {
    label: 'Apps and Programs',
    icons: [
      'Logic Pro',
      'Arduino',
      'Audacity',
      'Clerk',
      'Google Suite',
      'ClickUp',
      'GitHub',
      'Git',
    ],
    iconImages: [
      '/icons/techicons/apple.png',
      '/icons/techicons/arduino.png',
      '/icons/techicons/audacity.png',
      '/icons/techicons/clerk2.png',
      '/icons/techicons/google.png',
      '/icons/techicons/clickup1.png',
      '/icons/techicons/github.png',
      '/icons/techicons/git.png',
    ],
    background: 'white',
  },
];

export default defineComponent({
  name: 'MainLayout',

  components: {
    InformationBlock,
    ButtonLink,
    SkillsBox,
  },

  setup() {
    return {
      blocks: blocks,
      linkBlocks: links,
      skills: skills,
    };
  },
});
</script>

<style></style>
