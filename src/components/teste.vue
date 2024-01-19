<template>
    {{ name }}
</template>

<script>
    export default {
        name: 'App',
        data() {
            return {
                name: 'Jhon Snow'
            }
        },

        //HOOKS
        beforeCreate() {
            console.log('beforeCreate');
            console.log('Estado: ',this.name);
            console.log('DOM: ', this.$el);
        },
        create() {
            console.log('create');
            console.log('Estado: ',this.name);
            console.log('DOM: ', this.$el);
        },
        beforeMount() {
            console.log('beforeMount');
            console.log('Estado: ',this.name);
            console.log('DOM: ', this.$el);
        },
        mounted() {
            console.log('mounted');
            console.log('Estado: ',this.name);
            console.log('DOM: ', this.$el);
        },
        beforeUnmount() {
            console.log('beforeUnmount');
            console.log('Estado: ',this.name);
            console.log('DOM: ', this.$el);
        },
        unmounted() {
            console.log('unmounted');
            console.log('Estado: ',this.name);
            console.log('DOM: ', this.$el);
        }
    }
</script>

<style>
    header {
        background: #000;
        color: #fff;
    }
</style>