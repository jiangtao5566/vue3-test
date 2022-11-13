<template>
  <h1>Vue3</h1>
  <h2>{{name}}</h2>
  <h2>{{age}}</h2>
  <h2>{{obj.xd}}</h2>
  <h2>{{obj.course}}</h2>
  <h2>{{list}}</h2>
  <button @click="xd">弹窗</button>
  <button @click="change">弹窗1</button>
  <button @click="changeC">弹窗2</button>
  <button @click="changeH">弹窗3</button>

</template>

<script>
import {ref, reactive} from 'vue'
export default {
  setup(){
    let name = ref('张三')
    let age = ref(18)
    
    let obj= reactive({
      xd:'小滴课堂',
      course:'vue3'
    })
    
    function xd(){
      alert(`你好，我是${name.value},今年${age.value}了`)
    }

    function change(){
      name.value='李四'
      age.value=19
    }

    function changeC(){
      obj.course='react'
    }

    let list = reactive(['吃饭','睡觉','敲代码'])

    function changeH() {
      list[2]='路i阿鲁'
    }

    return {
      name,
      age,
      obj,
      list,
      xd,
      change,
      changeC,
      changeH
    }
  }
}
</script>

<style scoped>

</style>
