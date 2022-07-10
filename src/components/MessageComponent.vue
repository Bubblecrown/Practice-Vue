<template>
    <div>
        <h1>CRUD VUE.JS</h1>
        <p>{{ info }}</p>
        <!-- <h1>It's a test measage props</h1> -->
    </div>
</template>

<script>
export default {
    name: 'messageComponent',
    props: [
        'info'
    ],
}
</script>

<style>
h1, p{
    color:#fff
}
</style>