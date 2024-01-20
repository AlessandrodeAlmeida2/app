<template>
    <div :class="baseClass">
        <slot />

        <button @click="onClick()">
            X
        </button>
    </div>
</template>

<script>
export default {
    props: {
        variant: {
            type: String,
            default: ''
        },
    },
    computed: {
        baseClass() {
            return [
                'alert',
                this.variant? `alert-${this.variant}`: ''
            ]
        }
    },
    methods: {
        onClick() {
            this.$emit('close')
            console.log('Clicou');
        }
    }
}
</script>

<style scoped>
    .alert {
        padding: 5px;
        border-radius: 6px;
        color: gray;
        background: #ddd;
    }

    .alert-success {
        background: #42b983;
        color: #fff;
        width: 250px;
        margin-left: 150px;
    }
    
    button {
        background: gray;
        margin-left: 10px;
        border-radius: 5px;
    }

</style>