<template>
  <slot-view></slot-view>
</template>

<script>
import SlotviewComponent from './components/SlotviewComponent.vue';
export default
{
   components:
   {
     'slot-view' :SlotviewComponent
  },
}
</script>