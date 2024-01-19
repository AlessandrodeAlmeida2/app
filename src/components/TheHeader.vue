<template>
    <header>
        Header
    </header>
    <div>

    </div>
    <label>Nome</label><br>
    <input v-model="name" type="text"><br>
    {{ name }}
    <br><br>
    <div>
        <label for="">Sports</label>
        <select v-model="sports">
            <option value="futebol">Futebol</option>
            <option value="skate">Skate</option>
            <option value="tenis">Tênis</option>
        </select><br>
        {{ sports }} <br>

        <div>
            <label for="">Newsletter</label>
            <input v-model="news" type="radio" value="sim">Sim 
            <input v-model="news" type="radio" value="nao">Não <br>
            {{ news }} <br>
        </div>

        <div>
            <label for="">Contrato</label>
            <input v-model="contrato" type="checkbox">
            <br>
            {{ contrato }} <br>
        </div>

        <div>
            <label for="">Cores</label>
            <input v-model="cores" type="checkbox" value="azul">Azul 
            <input v-model="cores" type="checkbox" value="vermelho">Vermelho <br>
            {{ cores }} <br>
        </div>
        <div>
            <button @click="onClick">
                Enviar
            </button><br><br>
        </div>

        <form action="https://google.com" @submit="onSubmit">
            <button type="submit">
                Google
            </button><br><br>
        </form>
    </div>
</template>

<script>
    export default {
        name: 'App',
        data() {
            return {
                name: 'Jhon Snow',
                sports: '',
                news: '',
                contrato: '',
                cores: []
            }
        },
        watch: {
            sports() {
                this.changeSports()
            }
        },
        methods: {
            onClick($evt) {
                console.log('click!', $evt)
            },
            onSubmit() {
                console.log('submit')
            },
            changeSports() {
                console.log('Ajax');
                console.log(this.sports);
            }
        } 
    }
</script>

<style>
    header {
        background: #000;
        color: #fff;
    }
</style>