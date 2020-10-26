<template>
  <div id="content">
      <div id="product" v-for="product in productData" :key="product">
          <ul :class="product.name.replace(/\s/g,'')">
              <li class="head">
                  {{ product.name }}
              </li>
              <li v-for="cat in product.category" :key="cat">
                  {{ cat }}
              </li>
          </ul>
      </div>
  </div>
</template>

<script>
export default {
    name: 'Content',
    props: {
        productData: {
            type: Array
        }
    },
    created: {
        function (){
            
        }
    }
}
</script>

<style scoped>


#product ul {
    display: flex;
    flex-flow: row wrap;
    list-style: none;
}

#product ul li{
    padding: 10px;
    font-family: Arial, Helvetica, sans-serif;
    height: 150px;
    line-height: 120px;
    text-shadow: white 0px 0px 10px;
    letter-spacing: 2px;
    font-size: 1.2em;
}
li.head{
    min-width: 120px;
    font-weight: bold;
}
ul.Bacon{
    background-image: url('../assets/bacon.jpg');
    background-position: center;
    background-size: cover;
}
ul.Fish{
    background-image: url('../assets/fish.jpg');
    background-position: center;
    background-size: cover; 
}
ul.Chicken{
    background-image: url('../assets/chicken.jpg');
    background-position: center;
    background-size: cover; 
}
ul.Beef{
    background-image: url('../assets/beef.jpg');
    background-position: center;
    background-size: cover; 
}
ul.SoySauce{
    background-image: url('../assets/soy.jpg');
    background-position: center;
    background-size: cover; 
}
ul.Milk{
    background-image: url('../assets/milk.jpg');
    background-position: center;
    background-size: cover; 
}
ul.Cheese{
    background-image: url('../assets/cheese.jpg');
    background-position: center;
    background-size: cover; 
}
ul.FryingPan{
    background-image: url('../assets/fryingpan.jpg');
    background-position: center;
    background-size: cover; 
}
ul.Egg{
    background-image: url('../assets/egg.jpg');
    background-position: center;
    background-size: cover; 
}
ul.Plates{
    background-image: url('../assets/plates.jpg');
    background-position: center;
    background-size: cover; 
}
ul.Pork{
    background-image: url('../assets/pork.jpg');
    background-position: center;
    background-size: cover; 
}
</style>