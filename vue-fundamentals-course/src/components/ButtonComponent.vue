<template>
    <button @click="count++">{{count}}</button>
</template>
<script>
export default {
    name : 'ButtonComponent',
    data(){
        return {
            count : 0
        }
    }
}
</script>