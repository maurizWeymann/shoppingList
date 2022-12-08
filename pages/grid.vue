<template>
  <div class="list-wrapper">
    <div v-if="!editable" class="edit-item list-item">
      <input 
        type="number" 
        class="amount"
        v-model="amount"
      >
      <p class="multiplier">
        X
      </p>
      <input 
        type="text" 
        class="description"
        v-model="description"
      >
      <select 
        class="packaging"
        v-model="packaging"
      >
        <option value="Stück">Stück</option>
        <option value="Kiste">Kiste</option>
        <option value="kg">kg</option>
      </select>
      <input
        class="additional"
        type="text"
        value="Was es sonst noch wichtiges gibt" 
      >
      <button class="save">SAVE</button>
      <button class="edit">EDIT</button>
      <button class="erase">DELETE</button>
    </div>
    <div v-if="!editable" class="list-item">
      <div class="static-amount">
        {{ amount }}
      </div>
      <p class="static-multiplier">
        X
      </p>
      <div class="static-description">
        {{ description }}
      </div>

      <div
        class="static-packaging"
      >
      {{ packaging }}
      </div>
      <input
        class="additional"
        type="text"
        value="Was es sonst noch wichtiges gibt" 
      >
      <button class="save">SAVE</button>
      <button class="edit">EDIT</button>
      <button class="erase">DELETE</button>
    </div>
  </div>
  
</template>

<script setup>

const editable = ref(false)

const amount = ref(0)
const description = ref("")
const packaging = ref() 


</script>

<style lang="sass">
html 
  --darkBg: #9f9f9f

.list-wrapper 
  width: 100%
  max-width: 800px
  height: 100vh
  padding:10px
  margin: auto
  background-color: var(--darkBg)

.list-item
  display: grid
  width: 100%
  background: #6f6f6f
  grid-template-columns: repeat(24, 1fr) 
  grid-template-rows: 1fr 1fr 1fr
  gap: 5px
  padding: 5px
  
.amount
  grid-area: 1 / 1 / 1 / 5
  font-weight: bold

.static-amount
  grid-area: 1 / 1 / 1 / 3
  font-weight: bold
  margin: auto

.multiplier
  grid-area: 1 / 5 / 1 / 6
  color: #fff
  font-weight: bold
  margin: auto

.static-multiplier
  grid-area: 1 / 3 / 1 / 4
  color: #fff
  font-weight: bold
  margin: auto 0

.description
  grid-area: 1 / 6 / 1 / 18

.static-description
  grid-area: 1 / 4 / 1 / 18
  font-weight: bold
  margin: auto 0

.packaging
  grid-area: 1 / 18 / 1 / 25
  font-weight: bold

.static-packaging
  grid-area: 1 / 18 / 1 / 25
  font-weight: bold
  margin: auto 0

.additional
  grid-area: 2 / 1 / 2 / 25

button
  font-weight: bold

.save
  grid-area: 3 / 1 / 3 / 10

.edit
  grid-area: 3 / 10 / 3 / 18

.erase
  grid-area: 3 / 18 / 3 / 25


</style>