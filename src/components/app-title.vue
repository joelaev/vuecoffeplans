<template>
    <div class="content">
        <h1  class="title">
          
            {{title}}</h1>
        
        </div>
      </template>
<script setup>
defineProps({
  title :{
    type: String,
    required: true,
  },
});
</script>