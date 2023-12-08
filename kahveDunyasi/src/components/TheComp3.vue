<template>
    <q-page class="row items-center justify-evenly">
      <example-component
        title="Example component 3"
        active
        :todos="todos"
        :meta="meta"
      ></example-component>
    </q-page>
  </template>
  
  <script setup lang="ts">
  import { Todo, Meta } from 'components/models';
  import ExampleComponent from 'components/ExampleComponent.vue';
  import { ref } from 'vue';
  
  const todos = ref<Todo[]>([
    {
      id: 1,
      content: 'ct1 3',
    },
    {
      id: 2,
      content: 'ct2 3',
    },
    {
      id: 3,
      content: 'ct3 3',
    },
    {
      id: 4,
      content: 'ct4 3',
    },
    {
      id: 5,
      content: 'ct5 3',
    },
  ]);
  const meta = ref<Meta>({
    totalCount: 1200,
  });
  </script>
  