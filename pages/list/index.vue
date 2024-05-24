<template>
  <div>
    <p> Displaying back-end data in a grid:</p>
    <div class="grid grid-cols-5 gap-3">
      <div v-for="p in products.concepts" :key="p.code">
        <p> Display: {{p.display}} </p> 
        <p> Code: {{p.code}} </p> 
        <p> Version: {{p.version}} </p> 
      </div>
    </div>
  </div>
</template>

<script setup>
  const URL1 = 'https://dnpm.bwhealthcloud.de/api/coding/codesystems?uri=http://fhir.de/CodeSystem/bfarm/icd-10-gm&filter=is-a-category';
  const { data: products } = await useFetch(URL1)
 
  definePageMeta({
      layout: "default",
    })
  </script>
