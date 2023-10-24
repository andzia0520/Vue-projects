<template>
  <ul>
    <resource-item
      v-for="resource in storedResources"
      :key="resource.id"
      :title="resource.title"
      :description="resource.description"
      :link="resource.link"
    ></resource-item>
    <!-- <li v-for="listItem in storedResources" :key="listItem.id">{{listItem.link}}</li> -->
  </ul>
</template>

<script>
import ResourceItem from './components/learning-recsources/RecsourceItem.vue';
export default {
  components: { ResourceItem },
  data() {
    return {
      storedResources: [
        {
          id: 'official -guide',
          title: 'Official guide',
          description: 'The official Vue documentation',
          link: 'https://vuejs.org',
        },
        {
          id: 'google',
          title: 'Google',
          description: 'Learn to google',
          link: 'https://google.pl',
        },
      ],
    };
  },
};
</script>
<style>
@import url('https://fonts.googleapis.com/css2?family=Jost&display=swap');
* {
  box-sizing: border-box;
}

html {
  font-family: 'Jost', sans-serif;
}

body {
  margin: 0;
}
</style>
