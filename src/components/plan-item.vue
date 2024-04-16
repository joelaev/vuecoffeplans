<template>
    <div class="plan">
        <div class="description">
          <span class="title">
            {{name}}👍🏻{{likes}}
          </span>
        </div>
      </div>
</template>
<script setup>
defineProps({
  name :{
    type: String,
    required: true,
  },
  likes :{
    type: Number,
    default: 0,
  }
});
</script>