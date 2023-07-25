<template>
<button class="calculator__key">{{ number }}</button>
</template>

<script>
    export default {
        name:"KeyButton",
        props:{
            number:{
                type:[Number,String]
            }
        }
    }
</script>

<style lang="scss" scoped>

</style>