<template>
  <div class="p-2 py-4 row">
    <div
      v-for="({id,name,code,mostRecentEdition,fractionName,fraction,order,year,value,type,fPhoto,bPhoto,date,count,zoneName,fullName,mapCode,continent,valuePerUSD}, i) of currencies" :key="i"
      class="col-md-3"
    >
      <div class="card border px-2 py-4 border-2 mx-1 my-2">
        <CardView        
          :title="zoneName +' ' + name"
          :img="fPhoto"
          :label="code + ' ' + value+ ' ' + type"
          :action="{
            color: mostRecentEdition === order ? 'success' : 'danger',
            label: 'View Details',
            link: {
              path: '/my-showroom/piece-details',
              query: { id },
            },
          }"
        />
      </div>
    </div>
  </div>
</template>

<script setup>
  import CardView from "./CardView";

  defineProps({
    currencies: {
      type: Array,
      default: [],
    },
  })
</script>
