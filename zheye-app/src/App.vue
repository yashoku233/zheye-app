<template>
  <div class="container">
    <global-header :user="currentUser" />
    <column-list :list="list" />
  </div>
</template>

<script lang="ts">
/* eslint-disable */
import 'bootstrap/dist/css/bootstrap.min.css';
import { defineComponent } from 'vue';
import { ColumnProps, UserProps } from './types/ColumnProps';
import ColumnList from './components/ColumnList.vue';
import GlobalHeader from './components/GlobalHeader.vue';

const currentUser: UserProps = {
  isLogin: true,
  name:'宵夜'
};
const testData: ColumnProps[] = [
  {
    id: 1,
    title: 'test1',
    description: '这是test1的专栏,有一段非常有意思的简介',
    avatar: 'dad',
  },
  {
    id: 2,
    title: 'test2',
    description: '这是test2的专栏,有一段非常有意思的简介',
    avatar: 'dad',
  },
  {
    id: 3,
    title: 'test3',
    description: '这是test3的专栏,有一段非常有意思的简介',
    avatar: 'dad',
  },
  {
    id: 4,
    title: 'test4',
    description: '这是test4的专栏,有一段非常有意思的简介',
    avatar: 'dad',
  },
];
export default defineComponent({
  components: {
    ColumnList,
    GlobalHeader,
  },
  setup() {
    return {
      list: testData,
      currentUser,
    };
  },
});
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
