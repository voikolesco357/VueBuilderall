<template>
    <input v-model="hello">
    <br><br>
    {{ hello }}
</template>

<script>
export default {
    data() {
        return{
            hello: "teste"
        }
    },  
}
</script>

<style>

</style>