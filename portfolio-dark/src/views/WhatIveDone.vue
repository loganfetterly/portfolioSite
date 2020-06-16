<template>
  <core-section id="what-ive-done">
    <abstract-3 />

    <core-heading>What I've done</core-heading>

    <v-col cols="12">
      <v-carousel
        :cycle="false"
        :height="650"
        :show-arrows="false"
        class="elevation-0"
        hide-delimiter-background
      >
        <v-carousel-item
          v-for="(project, i) in projects"
          :key="i"
        >
          <project :value="project" />
        </v-carousel-item>
      </v-carousel>
    </v-col>
  </core-section>
</template>

<script>
  export default {
    name: 'WhatIveDone',

    components: {
      Abstract3: () => import('@/components/Abstract3'),
      Project: () => import('@/components/Project'),
    },

    data: () => ({
      projects: [
        {
          name: 'Phoenix Empire Web Development',
          category: 'Front-end Web',
          src: 'C:/Work/Personal/PortfolioWebsite/portfolio-dark/src/assets/projects/phoenixEmpire.PNG',
        },
        {
          name: 'Data Visualizations for Edmonton Heritage Council',
          category: 'Data Visualization, Data Science',
          src: 'C:/Work/Personal/PortfolioWebsite/portfolio-dark/src/assets/projects/phoenixEmpire.PNG',
        },
        {
          name: 'Memory Game for Edmonton Public Library',
          category: 'Game Development, Graphics Engine',
          src: 'C:/Work/Personal/PortfolioWebsite/portfolio-dark/src/assets/projects/phoenixEmpire.PNG',
        },
      ],
    }),
  }
</script>
