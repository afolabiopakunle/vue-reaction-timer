<template>
<div class="block">
    {{ score }}
    <br>
    {{ summary }}
</div>
</template>

<script>

export default {
    name: 'ResultComponent',
    props: ['score'],
    data() {
        return {
            summary: null,
        }
    },
    methods: {

    },
    mounted() {
        if(this.score >= 500) {
            this.summary = 'Snail fingers'
        } else if(this.score >=200) {
            this.summary = 'Fast fingers'
        } else {
            this.summary = 'Ninja fingers'
        }
    }
}
</script>
<style scoped>

.block {
    width: 400px;
    border-radius: 20px;
    background-color: crimson;
    color: white;
    text-align: center;
    padding: 100px 0;
    margin: 40px auto;
    cursor: pointer;
}
</style>