<template>
    <div>
        <h3>{{ valor }}</h3>
        <div style="background: a.color">
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