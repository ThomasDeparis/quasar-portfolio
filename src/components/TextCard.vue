<template>
  <q-card class="q-ma-md col shadow-10" style="min-width: 350px">
    <q-card-section>
      <div class="text-center text-h4">
        <slot name="title"></slot>
      </div>
    </q-card-section>
    <q-card-section class="row text-body1 section text-center">
      <slot></slot>
    </q-card-section>
    <q-card-section class="row q-ma-sm justify-center absolute-bottom">
      <slot name="buttons"></slot>
    </q-card-section>
  </q-card>
</template>

<script>
import { defineComponent } from "vue";

export default defineComponent({
  name: "TextCard",
});
</script>

<style lang="scss" scoped>
.section {
  text-align: justify;
  display: block;
}
</style>
