<template>
  <div class="row">
    <div v-for="column in list" :key="column.id" class="col-4 mb-4">
      <div class="card h-100 shadow-sm">
        <div class="card-body">
          <img
            :src="column.avatar"
            class="round-circle boder-light w-25 my-3"
            :alt="column.title"
          />
          <h5 class="card-title">{{ column.title }}</h5>
          <p class="card-text text-left">{{ column.description }}</p>
          <a href="#" class="btn btn-primary">{{ '进入专栏' }}</a>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
/* eslint-disable */

import { defineComponent, PropType } from 'vue';
import { ColumnProps } from '../types/ColumnProps';

export default defineComponent({
  name: 'ColumList',
  props: {
    list: {
      type: Array as PropType<ColumnProps[]>,
      required: true,
    },
  },
});
</script>
<style></style>
