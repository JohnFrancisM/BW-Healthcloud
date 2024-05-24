<template>
  <p class="bold-text">Search function</p>
  <div>
    <label for="objectDropdown">Select a code:</label>
    <select id="objectDropdown" v-model="selectedObject">
      <option v-for="(object, index) in objects.concepts" :key="index" :value="object.display">
        {{ object.code }}
      </option>
    </select>
    <p>Selection: {{ selectedObject }}</p>
  </div>
</template>

<style>
.bold-text {
  font-weight: bold;
  text-decoration: underline;
}
</style>

<script>
import axios from 'axios';

export default {
  data() {
    return {
      objects: [],
      selectedObject: null
    };
  },
  mounted() {
    this.fetchObjects();
  },
  methods: {
    async fetchObjects() {
      try {
        const response = await axios.get('https://dnpm.bwhealthcloud.de/api/coding/codesystems?uri=http://fhir.de/CodeSystem/bfarm/icd-10-gm&filter=is-a-category');
        this.objects = response.data; 
      } catch (error) {
        console.error('Error fetching objects:', error);
      }
    }
  }
};
</script>