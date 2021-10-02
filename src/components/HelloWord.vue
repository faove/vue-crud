<template>
    <div id="app-2" class="hello">
        <input type="text" v-model="newdata" @keyup.enter="agregarData"> 
        <button v-on:click="agregarData">Agregar</button>
        <ul>
            <li v-for="d of datas">
                {{d.name}} - <input type="text" v-model.number="d.cantidad">
                <span v-if="d.cantidad === 0">Cantidad es cero</span>
                <button @click="d.cantidad++">+</button>
            </li>
        </ul>
        <h5>Total: {{ sumarData }}</h5>
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
            datas: [
                {name: 'Fran', cantidad: 10},
                {name: 'Lore', cantidad: 0}
            ],
            newdata: '',
            total:0
        }
    },
    methods:{
        agregarData () {
            this.datas.push({
                name: this.newdata, cantidad: 0
            });
            this.newdata = ''
        }
    },
    computed:{
        sumarData () {
            // console.log('dentro del for');
            this.total = 0;
            this.datas.forEach((element) => {
                this.total = this.total + element.cantidad;
            });
            
            // (dat of this.datas){
            //     this.total = this.total + dat.cantidad;
            // }
            return this.total;
            // return this.datas.reduce((sum,data) => {
            //     return sum + data.cantidad
            // },0)
        }
    }
}
</script>

<style>

</style>