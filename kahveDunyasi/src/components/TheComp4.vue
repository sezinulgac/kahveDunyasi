<template>
    <q-page class="row items-center justify-evenly">
      <example-component
        title="Example component 4"
        active
        :todos="todos"
        :meta="meta"
      ></example-component>
      <q-card v-for="todo in todos" :key="todo.id" class="q-mb-md" style="width: 300px;">
      <q-card-section>
        <q-card-title>{{ todo.content }}
        </q-card-title>
      </q-card-section>
    </q-card>
    </q-page>
  </template>
  
  <script setup lang="ts">
  import { Todo, Meta } from 'components/models';
  import ExampleComponent from 'components/ExampleComponent.vue';
  import { ref } from 'vue';
  
  const todos = ref<Todo[]>([
    {
      id: 1,
      content: 'ct1 4',
    },
    {
      id: 2,
      content: 'ct2 4',
    },
    {
      id: 3,
      content: 'ct3 4',
    },
    {
      id: 4,
      content: 'ct4 4',
    },
    {
      id: 5,
      content: 'ct5 4',
    },
  ]);
  const meta = ref<Meta>({
    totalCount: 1200,
  });
  </script>
  