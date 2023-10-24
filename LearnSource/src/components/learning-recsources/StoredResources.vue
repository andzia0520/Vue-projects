<template>
  <ul>
    <resource-item
      v-for="resource in resources"
      :key="resource.id"
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
  props: ['resources'],
  components: { ResourceItem },
};
</script>

<style scoped>

</style>
