<template>
  <div class="plan" :class="{ 'active-plan': selected }" @click="select">
    <div class="description">
      <span class="title">
        {{ name }}
      </span>
    </div>
  </div>
</template>

<script>
export default 
{
  props: 
  {
    name: { type: String, required: true },
    selected: { type: Boolean, default: false },
  },
  methods: {
    select() {
      this.$emit('select', this.name);
    },
  },
};
</script>

