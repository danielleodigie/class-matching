<template>
    <div class="search-container">
        <input type="text" :value="value" @input="updateValue" placeholder="Search by class" />
    </div>
  </template>
  
  <script setup>
    import { ref } from 'vue';

    const props = defineProps({
        value: String
    });

    const emit = defineEmits(['update:value']);

    const updateValue = (event) => {
    emit('update:value', event.target.value);
    };
  </script>