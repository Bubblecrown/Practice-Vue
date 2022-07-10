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
}
</script>

<style>
*{
	padding:0;
	margin:0;
	box-sizing:border-box;
}
h1, p{
    color:#fff
}
</style>