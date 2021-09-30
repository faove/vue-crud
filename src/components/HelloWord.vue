<template>
    <div class="hello">
        <h1>{{ msg2 }}</h1>
        <h1>{{ texto }}</h1>
    </div>
</template>

<script>
export default {
    name: "HelloWord",
    props: {
        msg: String
    },
    data(){
        return {
            msg2: "otro",
            texto: "hola desde el Hello World!!"
        }
    }
}
</script>

<style>

</style>