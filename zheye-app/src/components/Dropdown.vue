<template>
  <div class="dropdown" ref="dropDownRef">
    <a href="#" class="btn btn-outline-light my-2 dropdown-toggle" @click.prevent="toggleOpen">{{
      title
    }}</a>
    <ul class="dropdown-menu" :style="{ display: 'block' }" v-if="isOpen">
      <slot></slot>
    </ul>
  </div>
</template>

<script lang="ts" setup>
import { ref, watch } from 'vue';
import useClickOutside from '../hooks/useClickOutsilde';
const props = defineProps({
  title: {
    type: String,
    required: true,
  },
});

const isOpen = ref(false);
const dropDownRef = ref<null | HTMLElement>(null);

defineExpose({
  dropDownRef,
});

const isClickOutside = useClickOutside(dropDownRef);

watch(isClickOutside, () => {
  console.log(isClickOutside.value, isOpen.value)

  if (isClickOutside.value && isOpen.value) {
    isOpen.value = false;
  }
});

function toggleOpen() {
  isOpen.value = !isOpen.value;
}
</script>
