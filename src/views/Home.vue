<template>
  <div class="home">
    <h2>JSON Manipulation</h2>
    <div class="container">
      <div class="row mb-3 mx-auto justify-content-center">
        <div class="col-md-4 mt-4" v-for="product in product" :key="product.inventory_id">
          <CardProduct :product="product"/>
        </div>
      </div>
      <div class="row mb-3 mx-auto justify-content-center">
        <div class="col-md-4 mt-4" >
          <!-- <FilterElectronic :filterElectronic="filterElectronic" /> -->
        </div>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'
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
      product: [],
      filterElectronic: []
    };
  },
  methods: {
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
      .get("http://localhost:3000/data")
      // .then(function(response) {
      //   console.log(response);
      // })
      // .catch(function(error) {
      //   console.log(error);
      // });
      .then(response => this.setProduct(response.data))
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
