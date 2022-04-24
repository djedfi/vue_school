<template>
    <slot-item v-for="data in data_array" :key="data">
        {{data}}
        <template #description>
            <p>{{data}} are good for your health</p>
        </template>
        <template #button-text>Save</template>
    </slot-item>
    
</template>

<script>
    import SlotComponent from './SlotComponent.vue';
    export default 
    {
        components: 
        { 
            'slot-item': SlotComponent 
        },
        data(){
            return{
                data_array:['Bananas','Apple','Orange']
            };
        }
    }
</script>