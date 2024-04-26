<template>
    <div class="plans">
      <plan-picker-item 
      @select="printSelected"
      v-for="plan in plans" 
      :name="plan" v-bind:key="plan" />
      {{selectedPlan}}
    </div>
</template>

<script setup>
    import {ref} from 'vue';
    import planPickerItem from './plan-picker-item.vue';
   const plans = ref([
 "El sltero",
 "El adicto", 
 "El viajero",
 ]);
 const selectedPlan= ref(null)
 const printSelected= (playload)=>
 {
  selectedPlan.value = playload;
 }
</script>
