<template>
    <div class="plans">
      <plan-picker-item 
      @select="printSelected"
      v-for="plan in plans" 
      :name="plan" v-bind:key="plan" />
    </div>
</template>

<script setup>
    import {ref} from 'vue';
    import planPickerItem from './plan-picker-item.vue';
   const plans = ref([
 "el sltero",
 "el adicto", 
 "el viajero",
 ]);
 const printSelected= (payload)=>
 {console.log(`Se selecciono: ${payload}`);
}
</script>
