<template>
    <div>
        <Titulo texto="Titulo de mi blog"></Titulo>
        <!-- <button @click="consumirApi">Consumir Api</button> -->
        <div v-for="(articulo, index) in arrayBlog" :key="index">
            <RouterLink :to="`/blog/${articulo.id}`">
                {{ articulo.id }} - {{ articulo.title }}
            </RouterLink>
            
        </div>
    </div>
</template>

<script>
import Titulo from '../components/Titulo.vue';

export default {
  
    name: 'Vue3OptionApiCliRouterBlogView',

    components: { Titulo },

    data() {
        return {
            arrayBlog: []
        };
    },

    mounted() {
        
    },

    methods: {
        async consumirApi() {
            try {
                const res = await fetch('https://jsonplaceholder.typicode.com/posts')
                const array = await res.json()
                this.arrayBlog = array
                console.log(array);
            } catch (error) {
                console.log(error)
            }
        }
    },

    // sin funcion de flecha, ya que sino, no tiene acceso al this
    // codigo que se ejecuta antes de cargar el template
    created() {
        this.consumirApi()
    }
};
</script>

<style lang="scss" scoped>

</style>