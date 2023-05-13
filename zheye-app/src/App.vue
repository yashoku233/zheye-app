<template>
  <div class="contariner">
    <column-list :list="list" />
  </div>
</template>

<script lang="ts">
/* eslint-disable */
import 'bootstrap/dist/css/bootstrap.min.css'

import { defineComponent } from 'vue';
import ColumnList from './components/ColumnList.vue';
import { ColumnProps } from './types/ColumnProps'


const testData: ColumnProps[] = [
  {
    id: 1,
    title: 'test1',
    description: '这是test1的专栏,有一段非常有意思的简介',
    avatar: 'dad'
  },
  {
    id: 2,
    title: 'test2',
    description: '这是test2的专栏,有一段非常有意思的简介',
    avatar: 'dad'
  },
  {
    id: 3,
    title: 'test3',
    description: '这是test3的专栏,有一段非常有意思的简介',
    avatar: 'dad'
  },
  {
    id: 4,
    title: 'test4',
    description: '这是test4的专栏,有一段非常有意思的简介',
    avatar: 'dad'
  }
]
export default defineComponent({
  components: {
    ColumnList,
  },
  setup() {
    return {
      list: testData
    }
  }
})

</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
