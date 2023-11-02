<template>
  <div class="dropdown">
    <a href="#" class="btn btn-outline-light my-2 dropdown-toggle" @click.prevent="toggleOpen">{{
      title
    }}</a>
    <ul class="dropdown-menu" :style="{ display: 'block' }" v-if="isOpen">
      <slot></slot>
    </ul>
  </div>
</template>

<script lang="ts" setup>
import { ref } from 'vue';
const props = defineProps({
  title: {
    type: String,
    required: true,
  },
});

const isOpen = ref(false);

function toggleOpen () {
  isOpen.value = !isOpen.value;
}
</script>
