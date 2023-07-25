<script>
    export default {
        name:"Operatorbutton",
        data(){
            return{
                
            }
        },
        props:{
            operator:{
                type:String
            }
        }
    }
</script>

<template>
<button class="calculator__key calculator__key--operator">{{ operator }}</button>
</template>

<style lang="scss" scoped>

</style>