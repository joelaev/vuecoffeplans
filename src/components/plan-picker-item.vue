<template>
  <div  
  @click="select"
  :class="{'selected-plan':selected}"
      class="plan">
        <div class="description">
          <span class="title">
            {{name}} {{ selected ? "⭐":"" }}
          </span>
        </div>
      </div>
</template>

<script setup>
import {ref} from 'vue';
//creando un evento
const emit= defineEmits(['select']);
const props=defineProps({
  name :{
    type: String,
    required: true,
  },
});
const selected = ref (false);
const select=()=>{
  selected.value=true
  emit('select', props.name)
}
</script>
<style scoped>
.selected-plan{
  background-color: rgb(197, 88, 10)}
</style>