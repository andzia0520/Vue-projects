<template>
  <div>
    <base-card>
      <base-button
        @click="setSelectedTab('stored-resources')"
        :mode="storedResBtnMode"
        >Stored resources</base-button
      >
      <base-button
        @click="setSelectedTab('add-resource')"
        :mode="adddResBtnMode"
        >Add resource</base-button
      >
    </base-card>
    <keep-alive>
      <component :is="selectedTab"></component>
    </keep-alive>
  </div>
</template>

<script>
import AddResource from './AddResource.vue';
import StoredResources from './StoredResources.vue';

export default {
  components: { AddResource, StoredResources },
  data() {
    return {
      selectedTab: 'stored-resources',
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
  provide() {
    return {
      resources: this.storedResources,
      addResource: this.addResource,
    };
  },
  computed: {
    storedResBtnMode() {
      return this.selectedTab === 'stored-resources' ? null : 'flat';
    },
    adddResBtnMode() {
      return this.selectedTab === 'add-resource' ? null : 'flat';
    },
  },
  methods: {
    setSelectedTab(tab) {
      this.selectedTab = tab;
    },

    addResource(title, desc, url) {
      const newRes = {
        id: new Date().toISOString,
        title: title,
        description: desc,
        link: url,
      };
      this.storedResources.unshift(newRes);
      this.selectedTab = 'stored-resources';
    },
  },
};
</script>
