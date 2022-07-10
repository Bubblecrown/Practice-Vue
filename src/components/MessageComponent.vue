<template>
    <div>
        <h1>CRUD VUE.JS</h1>
        <p>{{ deInfo }}</p>
        <!-- <h1>It's a test measage props</h1> -->
    </div>
</template>

<script>
export default {
    name: 'messageComponent',
    props: [
        'deInfo'
    ],
    methods:{
        
    }
}
</script>

<style>

h1, p{
    color:#fff
}
</style>