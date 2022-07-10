<template>
    <div>
        <button @click="bParent">
            Clear
        </button>
    </div>
</template>

<script>
export default {
    name: 'buttonClear',
    data(){
        return{
            testEmit:[
            {
                name:'A'
            },
            {
                name:'B'
            },
            {
                name:'C'
            }
        ],
        }
    },
    methods:{
        // cls() {
        //     this.add = {
        //         name:'',
        //         age:''
        //     }
        // },
        
        bParent(){
            this.$emit('cls', this.testEmit)
        }
    }
}
</script>

<style>

</style>