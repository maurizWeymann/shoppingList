<script setup>
import { list } from 'postcss';

const props = defineProps({
  item: list
})

</script>

<template>
  <div>
    hallo
    {{ item }}

  </div>
</template>
