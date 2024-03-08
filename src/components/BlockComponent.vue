<template>
    <div @click="myResult" class="block" v-if="showBlock">Click me</div>
</template>
<script>
export default {
    props: ['delay'],
    data() {
        return {
            showBlock: false,
        }
    },
    methods: {
        myResult() {
            console.log('result');
        }
    },
    mounted() {
        console.log('Mounted');
        setTimeout(() => {
            this.showBlock = true;
            console.log(this.delay);
        }, this.delay)
    },

}</script>

<style>
.block {
    width: 400px;
    border-radius: 20px;
    background-color: #0FAF87;
    color: white;
    text-align: center;
    padding: 100px 0;
    margin: 40px auto;
    cursor: pointer;
}
</style>