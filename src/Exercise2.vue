<template>
    <div class="container">
        <div class="row" v-if="computedLength">
            <div v-for="(value,key) in computedColor" :key="key" class="col-4">
                        {{value}}
            </div>
        </div>

    </div>
</template>

<style scoped>

</style>

<script setup>
import {computed,ref,reactive} from 'vue'
    let colorArray = reactive(['red','green','blue','orange','gray','blue','gray']);

    let computedColor = computed(()=>{
        return colorArray.filter((value,index)=>
        {
                    return value !== 'blue'
        })
    })
    let computedLength = computed(()=>{
        return colorArray.length > 0 ? true : false
    })

    setTimeout(()=>{
        colorArray.push('white');
    },3000)
</script>
