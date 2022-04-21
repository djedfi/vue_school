<template>
  <div class="container mx-auto py-6">
    <div class="content">
      <h1 class="title">Coffee Plans</h1>

      <h2 class="subtitle">
        We travel the world to source the very best single origin coffee for you
      </h2>
      <plan-picker></plan-picker>
    </div>
  </div>
</template>

<script>
import PlanPicker from './components/PlanPicker.vue';
export default
{
   components:
   {
     'plan-picker' :PlanPicker
  },
}
</script>