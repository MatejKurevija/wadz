<template>
<v-container>
  <v-card
    class="mx-auto"
    max-width=""
  >
    <v-card-text>
     <strong>SHA:</strong> {{id}}
    </v-card-text>
      <v-card-text><strong> DETALJI:</strong> {{details}} </v-card-text>
      <div class="center">
        <v-card-actions>
         <router-link :to="{ name: 'kartice', params: { shaID: id }}">
             <v-btn
               text
                color="teal accent-4"
                 @click="Više"
                 > Više
              </v-btn>
         </router-link>
        </v-card-actions>
      </div>
  </v-card>
</v-container>
</template>


<script>
export default {
  name: "card",
  props: {
    id: String,
    details: String,
  },
};
</script>

<style>

.right{
    display: flex;
    justify-content: flex-end;


}
a{
    text-decoration: none;
}
</style>