<template lang="pug">
  .projects
    ul.projects__list
      li(v-for="project in projects")
        Project(
          :title="project.title"
          :description="project[$i18n.locale].description"
          :origin="project.origin"
          :url="project[$i18n.locale].url"
          :year="project.year"
        )
</template>

<script lang="ts">
import { projects } from '~/projects';
import Vue from 'vue';
export default Vue.extend({
  computed: {
    projects() {
      return projects;
    },
  },
});
</script>

<style lang="scss">
.projects {
  width: 100%;
  height: 100%;
  margin: 40px 0;

  @include e('list') {
    padding: 0;
    margin: 0;
    list-style: none;
    display: grid;
    grid-template-columns: repeat(1, 1fr);
    grid-auto-rows: auto;
    gap: $padding;

    @include bp('3') {
      grid-template-columns: repeat(2, 1fr);
    }

    @include bp('4') {
      grid-template-columns: repeat(3, 1fr);
    }

    @include bp('7') {
      grid-template-columns: repeat(4, 1fr);
    }
  }
}
</style>