<template>
    
  <div class="card-product">
    <div class="card" style="width: 18rem;">
      <!-- <img :src="'../assets/images/' + product.gambar " class="card-img-top" alt="..."> -->
      <div class="card-tittle border">

        <h4 class="m-2">{{product.name}}</h4>
      </div>
      <div class="card-body">
        <p class="card-text text-left"><strong>Type: </strong>{{product.type}}</p>
        <p class="card-text text-left"><strong>Purchased at: </strong>{{product.purchased_at}}</p>
        <p class="card-text text-left"><strong>Tags: </strong>{{product.tags[0]}}, {{product.tags[1]}}, {{product.tags[2]}} </p>
        <p class="text-left"><strong>Placement :</strong></p>
        <p class="card-text text-left">-Room No : {{product.placement.room_id}}</p>
        <p class="card-text text-left">-Name : {{product.placement.name}}</p>

        
        <!-- <router-link :to="'/foods/'+product.id" href="#" class="btn btn-success float-right">Pesan</router-link> -->
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "CardProduct",
  props: ["product"]
};
</script>

<style>
</style>