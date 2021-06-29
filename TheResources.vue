<template>
<div>
  <button @click="resourcesFunction('stored-resources')">
    Stored Resources
  </button>
  <button @click="resourcesFunction('add-resources')">Add Resources</button>
  <!-- <add-resources></add-resources>
    <stored-resources></stored-resources> -->
  <!-- <component :is="resourcesValue"></component> -->
  <add-resources v-if="resourcesValue === 'add-resources'" ></add-resources>
  <stored-resources v-if="resourcesValue === 'stored-resources'" ><stored-resources>
</div>
</template>

<script>
import AddResources from './AddResources.vue';
import StoredResources from './StoredResources.vue';

export default {
  components: {
    AddResources,
    StoredResources,
  },
  data() {
    return {
      resourcesValue: 'stored-resources',
    };
  },
  methods: {
    resourcesFunction(res) {
      this.resourcesValue = res;
    },
  },
};
</script>