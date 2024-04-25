<template>
    <div class="titulon">
        <div class="description">
          <span class="title">
            {{subtitle}}
          </span>
        </div>
      </div>
</template>
<script setup>
defineProps({
  subtitle :{
    type: String,
    required: true,
  },
});
</script>