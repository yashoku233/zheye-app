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
        <Dropdown :title="`你好, ${user.name}`">
          <dropdown-item> <a href="#" class="dropdown-item">新建文章</a></dropdown-item>
          <dropdown-item disabled> <a href="#" class="dropdown-item">编辑资料</a></dropdown-item>
          <dropdown-item> <a href="#" class="dropdown-item">退出登录</a></dropdown-item>
        </Dropdown>
      </li>
    </ul>
  </nav>
</template>

<script lang="ts" setup>
import { PropType } from 'vue';
import { UserProps } from '../types/ColumnProps';
import Dropdown from './Dropdown.vue';
import DropdownItem from './DropdownItem.vue';

const props = defineProps({
  user: {
    type: Object as PropType<UserProps>,
    required: true,
  },
});
</script>
