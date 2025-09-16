<template>
    <div>
        <h1>{{ sum }}</h1>
        <select v-model="n">
            <option value="1">1</option>
            <option value="2">2</option>
            <option value="3">3</option>
        </select>
        <button @click="addNum">点击num加{{n}}</button>
         <button @click="delNum">点击num减{{n}}</button>
    </div>
  
</template>

<script setup lang="ts" name="text">
import {ref} from 'vue'
  // 引入对应的useXxxxxStore	
import {useCountStore} from '../store/count'

import {storeToRefs} from 'pinia'
  // 调用useXxxxxStore得到对应的store
const sumStore = useCountStore()
const {sum}=storeToRefs(sumStore)
let n=ref(1)

function addNum(){
    sum.value+=Number(n.value);
}

function delNum(){
    sum.value-=Number(n.value);
}
</script>

<style>

</style>