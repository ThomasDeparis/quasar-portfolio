<template>
  <div class="row fit justify-center text-center">
    <h3 class="text-primary"><slot></slot></h3>
  </div>
</template>

<script>
import { defineComponent } from "vue"

export default defineComponent({
  name: 'SectionTitle'  
})
</script>
