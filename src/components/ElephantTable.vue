<template>
  <div> 
    <v-data-table
      :headers="headers" 
      :items="elephants"
      :items-per-page="5"
      class="elevation-1"
    ></v-data-table>
    <v-btn  @click = "getElephants">
    </v-btn>
  </div>



</template>

<script>
  export default {
    name: 'ElephantTable',

    data: () => ({
      elephants: [], 
      
      headers: [
        {
          value: "sha",
          text: "имя"
        },
        {
          value: "url",
          text: "спешиал"
        },
        {
          value: "node_id",
          text: "Фиктионал"
        }
      ]
    
    }),
    methods: {
      getElephants() {
         fetch('https://api.github.com/repos/javascript-tutorial/en.javascript.info/commits')
          .then(response => response.json())
          .then(commits => {
             console.log(commits);
             this.elephants = commits
          });
      }
    }
  }
</script>
