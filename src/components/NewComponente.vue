<template>
    <div>
        <h3>{{ valor }}</h3>
        <div class="background: red">
            <HelloWord></HelloWord>
        </div>

    </div>
</template>

<script>
import HelloWord from './HelloWord.vue';

export default {
    name: "newcomponente",
    components: { HelloWord },
    data(){
        return{
            valor: "valor del componente"
        };
    },
}
</script>