<template>
    <div class="container mt-5">
        <div :class="['p-3','text-white',fondo]">
           <p> Lorem ipsum dolor sit amet consectetur adipisicing elit. Laudantium modi optio laborum sunt. Officia amet, nisi reiciendis, at voluptate enim aspernatur quibusdam molestias fugit delectus tempore laudantium esse dolorem numquam.</p>
        </div>
        <input type="text" class="form-control my-3" v-model="fondo">
        <div class="text-white p-3" :class="{'bg-info' : color, 'bg-success' : !color}">
            <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Ut eaque aliquam earum labore, pariatur facilis ipsum! Perferendis, adipisci dicta, accusantium omnis amet nihil cum voluptates laborum ullam nam, impedit sint.
            </p>
        </div>
        <button class="btn btn-primary" @click="color = !color">Press</button>
    </div>
</template>

<script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
<script>

export default {
    name: "nameclass",
    props: {
        msg: String
    },
    data () {
        return{
            fondo: 'bg-warning',
            color: true
        }
    },
    methods: {
        
    }

}

</script>