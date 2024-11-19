<script>
import Category from './components/Category.vue';
import Promotion from './components/Promotion.vue'


import axios from 'axios';
export default {
  name: "App",
  components: {
    Category,
    Promotion,
  },
  data() {
    return {
      promotions : [],
      categories: [],

      
    }

  },
 

     

  methods: {
    fetchCategory() {
      axios
        .get("http://localhost:3000/api/categories")
        .then((response) => {


          console.log(response.data); // Access the data

          this.categories = response.data;
        })
        .catch((error) => {
          console.error("Error fetching data:", error);
        });
    },

    fetchPromotion() {
      axios
        .get("http://localhost:3000/api/promotions")
        .then((response) => {
          console.log(response.data); // Access the data

          this.promotions = response.data;
        })
        .catch((error) => {
          console.error("Error fetching data:", error);
        });
    },

    
  },

  async mounted() {
    this.fetchCategory();
    this.fetchPromotion();

  },


  



}


</script>

<template>


  <main class="main_content">
    <div class="category_container">
      <Category v-for="product in this.categories" :key="product.name" :bgColor="product.color" :imageSrc="product.image"
        :title="product.name" :items="product.productCount" />

    </div>
    <div class="Promotion_container">
      <Promotion v-for="promotion in promotions" 
      :bgColor="promotion.color"
      :key="promotion.title"
      :imageSrc="promotion.image"
      :content="promotion.title"
      :btn-color="promotion.buttonColor"
      />

    </div>

  </main>

</template>

<style>
.main_content {
  min-height: 100vh;
  padding-bottom: 2rem;
  display: flex;
  flex-direction: column;
  align-items: center;


}

.main_content .category_container {
  gap: 1.2rem;
  width: 100%;
  padding: 1rem;
  display: grid;
  place-items: center;
  grid-template-columns: repeat(auto-fit, minmax(6.5rem, 1fr));
  height: auto;
}
.main_content .Promotion_container{
  width: 96%;
  height: auto;
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(27rem, 1fr));
  place-items: center;
  row-gap: 1rem;
}

</style>
 