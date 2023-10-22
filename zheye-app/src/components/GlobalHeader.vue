<template>
  <nav class="navbar navbar-dark bg-primary justify-content-between mb-4 px-4">
    <a class="navbar-brand" href="#">宵夜专栏</a>
    <ul class="list-inline mb-0" v-if="!user.isLogin">
      <li class="list-inline-item">
        <a href="#" class="btn btn-outline-light">{{ '登录' }}</a>
      </li>
      <li class="list-inline-item">
        <a href="#" class="btn btn-outline-light">{{ '注册' }}</a>
      </li>
    </ul>
    <ul class="list-inline" v-else>
      <li class="list-inline-item">
        <Dropdown :title="title" />
      </li>
    </ul>
  </nav>
</template>

<script lang="ts" setup>
import { PropType } from 'vue';
import { UserProps } from '../types/ColumnProps';
import Dropdown from './Dropdown.vue';

const title = 'zjw'
const props = defineProps({
  user: {
    type: Object as PropType<UserProps>,
    required: true,
  },
});
</script>
