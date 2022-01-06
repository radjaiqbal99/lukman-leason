<template>
  <div class="home">
    <h2>JSON Manipulation</h2>
    <div class="container">
      <button @click="target = ''">All</button>
      <button @click="target = 'furniture'">Furniture</button>
      <button @click="target = 'electronic'">Elektronic</button>
      <div class="row mb-3 mx-auto justify-content-center">
        <!-- <div class="col-md-4 mt-4" v-for="(data,index) in product" :key="index"> -->
          <!-- <CardProduct :product="data"/> -->
          <!-- <CardProduct v-if="data.type == 'furniture'" :product="data"/> -->
          <CardProduct :target="target" :product="product"/>
        <!-- </div> -->
      </div>
      <!-- <h1>Elektronic</h1>
      <div class="row mb-3 mx-auto justify-content-center">
        <div class="col-md-4 mt-4" v-for="(data,index) in product" :key="index">
          <CardProduct v-if="data.type == 'electronic' " :product="data"/>
        </div>
      </div> -->
      <!-- <div class="row mb-3 mx-auto justify-content-center">
        <div class="col-md-4 mt-4" v-for="(data,index) in product" :key="index">
          <FilterElectronic v-if="data.type == 'electronic' " :filterElectronic="filterElectronic" />
        </div>
      </div> -->
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'
// import dataJson from '../../public/db.json'
import axios from "axios";
import CardProduct from "@/components/CardProduct.vue";
// import FilterElectronic from "@/components/FilterElectronic.vue";

export default {
  name: "Home",
  components: {
    // HelloWorld
    CardProduct
    // FilterElectronic
  },

  data() {
    return {
      product: null,
      filterElectronic: [],
      target : ''
    };
  },
  methods: {
    change(payload){
      this.target = payload
    },
    setProduct(data) {
      this.product = data;
    }
    //  filterElectronic (catName){
    //    this.product = this.product.filter((product)=>{
    //      return product.type === catName
    //    })
    //  }

    // setFilterElectronic(){
    //   axios
    //   .get("http://localhost:3000/data")
    //   .then(response => {
    //     const products = response.data
    //     this.filterElectronic = products.filter(product => product.type.includes('electronic'))

    //   })

    // }
  },
  mounted() {
    axios
      .get("db.json")
      // .then(function(response) {
      //   console.log(response);
      // })
      // .catch(function(error) {
      //   console.log(error);
      // });
      .then(response => this.setProduct(response.data))
      // .then(response => console.log(response))
      .catch(error => console.log("Gagal:", error));
  },

  // computed() {
  //   // filteredElectronic() {
  //   //         // return this.product.filter(product => product.electronic === 'electronic');
  //   //         return this.product.filter(product => product.type.includes('food'))
  //   // }
  // }
};
</script>
