<template>
    <div>
        <Titulo texto="Ruta dinamica"></Titulo>
        <h2>Parámetro: {{ $route.params.id }}</h2>
        <h3> {{articulo.id}} - {{ articulo.title }}</h3>
        <p>{{ articulo.body }}</p>
    </div>
</template>

<script>
import Titulo from '../components/Titulo.vue';

export default {
    name: 'Vue3OptionApiCliRouterArticulo',

    components: { Titulo },

    data() {
        return {
            articulo: {}
        };
    },

    mounted() {
        
    },

    methods: {
        async consumirArticulo(){
            try {
                const res = await fetch(`https://jsonplaceholder.typicode.com/posts/${this.$route.params.id}`) 
                const objeto = await res.json();
                this.articulo = objeto
                console.log(objeto)
            } catch (error) {
                console.log(error)
            }
        }
    },

    created() {
        this.consumirArticulo();
    }
};
</script>

<style lang="scss" scoped>

</style>