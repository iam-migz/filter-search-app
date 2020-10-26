<template>
  <div id="container">
    <Search @new-input="fromSearch" />
    <Tags @clicked-tag="fromTags" />
    <Content :product-data="product" />
  </div>  
</template>

<script>

import Search from './components/Search';
import Tags from './components/Tags';
import Content from './components/Content';

export default {
  name: 'App',
  data(){
    return {
      product: this.getProducts()
    }
  },
  components: { Search, Tags, Content },
  methods: {
    getProducts(){
      return [{id:1,name:'Bacon',category:['Meat']},{id:2,name:'Fish',category:['Seafood','Fresh']},{id:3,name:'Chicken',category:['Poultry','Fresh']},{id:4,name:'Beef',category:['Meat']},{id:5,name:'Soy Sauce',category:['Sauce','Seasoning']},{id:6,name:'Milk',category:['Dairy']},{id:7,name:'Cheese',category:['Dairy']},{id:8,name:'Frying Pan',category:['Utensil','Cookware']},{id:9,name:'Egg',category:['Dairy']},{id:10,name:'Plates',category:['Utensil']},{id:11,name:'Pork',category:['Meat']}]
    },
    fromSearch(value){
      this.product = this.getProducts();
      if(value != ''){
        this.product = this.product.filter(elem => elem.name.toLowerCase() == value.toLowerCase() ||elem.category.find(cat => cat.toLowerCase() ==  value.toLowerCase()));
      }
    },
    fromTags(value){
      this.product = this.getProducts();
      if(value != 'Reset'){
        this.product = this.product.filter(elem => elem.category.find(cat => cat == value));
      }
    }
  }
}
</script>

<style>
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
#container {
  background: #f4f4f4;
  max-width: 1080px;
  margin: 0 auto;
  margin-top: 50px;
}
</style>
