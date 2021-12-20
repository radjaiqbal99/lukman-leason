<template>

  <div>
    <h2>Filter Electronic</h2>
    <p 
    v-for="filter in filters" 
    :key="filter"
    @click="()=> filterElectronic(filter)"
    >
    {{filter}}
    </p>
  </div>
</template>

<script>
const filters = [
    'electronic',
    'furniture'
]

export default {
    name: "FilterElectronic",
    props: ["filterElectronic"],
    data(){
        return{
            filters
        }
    }
}
</script>

<style>
</style>
