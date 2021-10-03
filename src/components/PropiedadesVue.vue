<template>
    <div id="app-2" class="propiedades">
        <h5>{{mensaje}}</h5>
        <h5>Invertido: {{invertido}}</h5>
        <input type="text" class="form-control" v-model="mensaje">
        <button class="btn btn-primary" @click="contador++">+</button>
        <button class="btn btn-danger" @click="contador--">-</button>
        <h3>{{contador}}</h3>
        <div class="progress">
            <div class="progress-bar " role="progressbar" 
            :style="{'width': contador+'%'}" aria-valuenow="25" aria-valuemin="0" 
            aria-valuemax="100"
            :class="color"
            >{{contador}}%</div>
        </div>
    </div>
</template>

<script>
export default {
    name: "propiedades",
    props: {
        msg: String
    },
    data(){
        return {
            datas: [
                {name: 'Fran', cantidad: 10},
                {name: 'Lore', cantidad: 0}
            ],
            mensaje: 'Epale es una prueba',
            contador:0
        }
    },
    computed:{
        invertido(){
            return this.mensaje.split('').reverse().join('');
        },
        color(){
            return{
                'bg-success' : this.contador <= 10,
                'bg-warning' : this.contador > 10 && this.contador <=20,
                'bg-danger'  : this.contador > 20
            }
        }
    }
}
</script>