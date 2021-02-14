<template>
  <v-data-table
    :headers="headers" 
    :items="elephants"
    :items-per-page="5"
    class="elevation-1"
  ></v-data-table>
</template>

<script>
  export default {
    name: 'ElephantTable',

    data: () => ({
      elephants: [], 
      
      headers: [
        {
          value: "name",
          text: "имя"
        },
        {
          value: "species",
          text: "спешиал"
        },
        {
          value: "fictional",
          text: "Фиктионал"
        }
      ]
    
    }),
  }
</script>
