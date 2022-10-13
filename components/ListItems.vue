
<script setup>

const items = ref([
  {
    itemID: "item-1",
    description: "Brot",
    amount: 1,
    packaging: "Glas",
    additionalInfo: "Vollkorn lieber als Weißbrot",
    category:"Kühl"
  },
  {
    itemID: "item-2",
    description: "Wurst",
    amount: 10,
    packaging: "Stück",
    additionalInfo: "Nur Geflügel",
    category:"Fleisch"
  }
])

const newItem = ref("")


</script>

<template>
  <div v-for="item in items" :key="item.itemID" class="card m-2">

  <div class="card-header-new"> 
    <div class=" columns is-mobile">
      <div class="column is-one-fifth ">
        <input 
          type="number" 
          class="is-size-6 has-text-weight-bold" 
          v-model="item.amount"
        >
      </div>
      <div class="column"> 
        <input 
          type="text" 
          class="is-size-6 has-text-weight-bold	" 
          v-model="item.description"
        >
      </div>
      <div class="column"> 
        <input 
          type="text" 
          class="is-size-6 has-text-weight-bold	" 
          v-model="item.description"
        >
      </div>
    </div>
  </div>

  <header class="card-header"> 
    <p class="card-header-title">
        {{ item.amount }} x {{ item.description }} {{ this.additional }}
    </p>
    <button 
      class="card-header-icon" 
      aria-label="more options"
      @click="this.additional = !this.additional"
      >
      <span class="icon">
        <i class="fas fa-angle-down" aria-hidden="true"></i>
      </span>
    </button>
  </header>

  <div v-if="true" class="additionalInformation">
      <div class="card-content">
    <div class="content">
      {{ item.additionalInfo }}
    </div>
    </div>
    <footer class="card-footer">
      <a href="#" class="card-footer-item">Save</a>
      <a href="#" class="card-footer-item">Edit</a>
      <a href="#" class="card-footer-item">Delete</a>
    </footer>
  </div>

</div>
</template>

<style lang="sass">
.card-header-new
  box-shadow: 0 0.125em 0.25em rgb(10 10 10 / 10%)

.column
  position: relative

input
  font-weight: 700
  padding-top: 0.75rem
  padding-right: 1rem
  padding-bottom: 0.75rem
  padding-left: 1rem
  border: none


</style>