<template>
  <div ref=planProper style="border: red double 10px;" class="plans">
    <plan-picker-item
      @select="printSelected"
      :selectedPlan="selectedPlan"
      v-for="plan in plans" 
      :name="plan" 
      v-bind:key="plan" />
      <p>couter:{{ counter }}</p>
       </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue';
import planPickerItem from './plan-picker-item.vue';
const plans = ref([
  "El soltero",
  "El adicto",
  "El viajero",]);

  const planProper=ref (null)
  const selectedPlan = ref(null);

  const printSelected = (playload) => {
    selectedPlan.value = playload;
  }
  //creando referencia reactiva para un contador
  const counter=ref(0);
 
//creando un metodo para increementar el contador este solo acepta milisegundos
const processId= setInterval(()=>{
  console.log('incrrementando contador')
  counter.value++
},1000);

    //regitrando el CB (call back) 
  onMounted(()=>{
    console.log(planProper.value)
  });
  //registranfo CB de unMounted
  onUnmounted(()=>{
    console.log('Componente plan Picker desmontado')
    clearInterval(processId);
  });
</script>