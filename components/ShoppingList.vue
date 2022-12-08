<script setup>
  const items = ref([
  {
    itemID: "item-1",
    description: "Brot",
    amount: 1,
    packaging: "Stück",
    additionalInfo: "Vollkorn lieber als Weißbrot",
    category:"Kühl"
  },
  {
    itemID: "item-2",
    description: "Wurst",
    amount: 10,
    packaging: "Pack",
    additionalInfo: "",
    category:"Fleisch"
  },
  {
    itemID: "item-3",
    description: "Gouda",
    amount: 1,
    packaging: "Groß",
    additionalInfo: "von Metro Hausmarke",
    category:"Käse"
  }
])

  
</script>

<template>
  <div v-for="item in items" :key="item.itemID">
    <ListItems 
    :item = "item"
    />
  </div>    
</template>

<style>

</style>