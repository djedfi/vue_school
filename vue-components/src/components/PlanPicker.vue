<template>
  <div class="plans">
    <plan-picker-item
      v-for="plan in plans"
      :name="plan"
      :selected="plan === selectedPlan"
      @select="selectPlan">
    </plan-picker-item>
  </div>
  <h2 class="subtitle" v-if="selectedPlan">You have selected: {{selectedPlan}}</h2>
</template>

<script >
import PlanPickerItem from './PlanPickerItem.vue';
export default 
{
    components: 
    { 
      'plan-picker-item': PlanPickerItem 
    },
    data() 
    {
        return {
            plans: ['The Single', 'The Curious', 'The Addict'],
            selectedPlan: null,
        };
    },
    methods: 
    {
        selectPlan(plan) 
        {
            this.selectedPlan = plan;
        },
    },
};
</script>


