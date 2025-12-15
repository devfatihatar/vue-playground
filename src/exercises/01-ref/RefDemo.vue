<script setup>
// ref: tek bir değeri reaktif hale getirir (reactive = değişince UI güncellenir)
import { computed } from "@vue/reactivity"
import { ref } from "vue"

const count = ref(0)  //count.value = gerçek değer
const name = ref("Fatih") //name değişkenini reactive hale getirdik.

//count değişkenindeki sayıyı artıran fonksiyon.
function increment(){
    count.value++
}

const upperName = computed(() => {
    return name.value.toUpperCase()
})
</script>

<template>
    <div style="padding:16px">
        <h2>01 - ref demo</h2>

        <p><b>Count:</b> {{  count  }}</p>
        <button @click="increment">Increase</button>
        
        <hr />

        <label>
            <b>name:</b>
            <input v-model="name" placeholder="Type your name">
        </label>
        <p>Hello, {{ name }}</p>
        <p>Uppercase: {{ upperName }}</p>
    </div>
</template>
