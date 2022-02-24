<template>
  
      <h1 class="font-extrabold text-3xl mb-6">Home</h1>
      
      <p class="mb-6">Name in store is: {{ name }}</p>

      <input v-model="newName" type="text" class="p-2 mr-2 rounded border border-gray-800">

      <button @click="saveName" class="p-2 text-gray-50 bg-indigo-500 rounded">Submit</button>
  
</template>

<script setup>
import { useStore } from 'vuex'
import { computed, ref } from 'vue'
const store = useStore()
const name = computed(() => {

  return store.state.user.name

})

const newName = ref('')

function saveName() {

  store.dispatch('saveName', newName.value)

}
</script>
