<template>
    <div>
        <input type="checkbox" v-model="done">
        <span :class="{ done }">
            <slot></slot>
        </span>
        <slot name="description"></slot>
        <button type="button"><slot name="button-text">Default</slot></button>
    </div>
</template>

<script>
export default {
    data(){
        return{
            done: false
        };
    }
}
</script>
<style>
    .done{
        color:green;
        text-decoration: line-through;
    }
</style>