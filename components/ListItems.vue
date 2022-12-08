
<script setup>

import { list } from 'postcss';


const props = defineProps({
  item: list
})

const newItem = ref("")

const editable = ref(false)

const edit = () => {
  editable.value = !editable.value
  //console.log("thisItem was checked")
}



</script>

<template>
  {{ thisElement }}
  <!-- Input für Item, wenn editable true -->
    <div v-if="editable" class="edit-item"> 
      <form action="">
        <div class="columns is-mobile">
          <div class="column is-1 bg-black">
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
              type="drop" 
              class="is-size-6 has-text-weight-bold	" 
              v-model="item.description"
            >
          </div>
      </div>
      </form>
    </div>

  <header v-if="!editable" class="card-header" @click="edit()" > 
    <p class="card-header-title" >
        {{ item.amount }} x {{ item.description }} - {{ item.packaging }}
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
    <footer v-if="editable" class="card-footer">
      <a 
        href="#" 
        @click="edit()"
        class="card-footer-item">Save</a>
      <a 
        href="#"
        @click="edit()"
        class="card-footer-item">Edit</a>
      <a 
        href="#" 
        class="card-footer-item">Delete</a>
    </footer>
  </div>
</template>

<style lang="sass">
.edit-item
  background-color: gray

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