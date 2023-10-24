<template>
  <div>
    <the-header title="RememberMe"></the-header>
    <stored-resources :resources="storedResources"></stored-resources>
  </div>
</template>

<script>
import TheHeader from './components/layouts/TheHeader.vue';
import StoredResources from './components/learning-recsources/StoredResources.vue';

export default {
  components: { StoredResources, TheHeader },
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
