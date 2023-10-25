<template>
  <ul>
    <resource-item
      v-for="resource in resources"
      :key="resource.id"
      :id="resource.id"
      :title="resource.title"
      :description="resource.description"
      :link="resource.link"
    ></resource-item>
    <!-- <li v-for="listItem in storedResources" :key="listItem.id">{{listItem.link}}</li> -->
  </ul>
</template>

<script>
import ResourceItem from './ResourceItem.vue';

export default {
  inject: ['resources'],
  components: { ResourceItem },
};
</script>

<style scoped>
ul {
  list-style: none;
  margin: 0;
  padding: 0;
  margin: auto;
  max-width: 40rem;
}
</style>
