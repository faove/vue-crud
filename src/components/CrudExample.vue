<template>
    <div class="container mt-5">
        <h1>{{ titulo }}</h1>

        <input type="text" class="form-control my-3" v-model="nuevatarea" v-on:keyup.enter="AgregarTarea">
        <button class="btn btn-primary" @click="AgregarTarea">Add</button>
        
        <div class="mt-3" v-for="(item, index) of tareas">
            <div role="alert" :class="['alert', item.estado ? 'alert-success' :'alert-danger']">
                <div class="d-flex justify-content-between align-items-center">
                    <div>
                        {{index}} - {{item.nombre}} - {{item.estado}}
                    </div>
                    <div >
                        <button class="btn btn-success btn-sm" @click="editarTarea(index)">OK</button>
                        <button class="btn btn-danger btn-sm" @click="eliminarTarea(index)">X</button>
                    </div>
                </div>
            </div>
        </div>
        
    </div>
</template>

<script>
export default {
    name: "nameclass",
    props: {
        msg: String
    },
    data () {
        return{
            titulo: "CRUD",
            tareas: [],
            nuevatarea: ''
        }
    },
    methods: {
        AgregarTarea: function(){
            this.tareas.push({
                nombre: this.nuevatarea,
                estado: false
            });
            localStorage.setItem('crud-vue',JSON.stringify(this.tareas));
            this.nuevatarea = '';
        },
        editarTarea: function(index){
            this.tareas[index].estado = true
            localStorage.setItem('crud-vue',JSON.stringify(this.tareas));
        },
        eliminarTarea: function(index){
            this.tareas.splice(index,1)
            localStorage.setItem('crud-vue',JSON.stringify(this.tareas));
        }
    },
    created: function(){
        let datosDB = JSON.parse(localStorage.getItem('crud-vue'));
        if (datosDB === null){
            this.tareas = [];

        }else{
            this.tareas = datosDB;
        }
    }
}
</script>