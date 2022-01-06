<template>
  <div>
    <div class="card-product">
      <div v-for="(data, index) in product" :key="index">
        <div v-if="data.type == target || target === ''" class="card" style="width: 18rem;">
          <div class="card-tittle border">
            <h4 class="m-2">{{data.name}}</h4>
          </div>
          <div class="card-body">
            <p class="card-text text-left"><strong>Type: </strong>{{data.type}}</p>
            <p class="card-text text-left"><strong>Purchased at: </strong>{{data.purchased_at}}</p>
            <p class="card-text text-left"><strong>Tags: </strong>{{data.tags[0]}}, {{data.tags[1]}}, {{data.tags[2]}} </p>
            <p class="text-left"><strong>Placement :</strong></p>
            <p class="card-text text-left">-Room No : {{data.placement.room_id}}</p>
            <p class="card-text text-left">-Name : {{data.placement.name}}</p>
          </div>
        </div>
      </div>
    </div>
</div>
</template>

<script>
export default {
  name: "CardProduct",
  props: ["product","target"]
};
</script>

<style>
</style>