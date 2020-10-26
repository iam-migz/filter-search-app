<template>
  <div id="tags">
      <ul>
          <li @click="send(tag,event)" v-for="(tag, index) in tags" :key="index">{{ tag }}</li>
      </ul>
  </div>
</template>

<script>
export default {
    name: 'Tags',
    data() {
        return {
            tags: ['Meat','Seafood','Fresh','Poultry','Sauce','Seasoning','Dairy','Utensil','Cookware','Reset'],
            previous: '',
        }
    },
    methods: {
        send(tag){
            if(this.previous == event.target){
                 event.target.classList.remove('current');
                 this.previous = '';
                 this.$emit('clicked-tag', 'Reset');
            }else{
                if(this.previous != ''){
                    this.previous.classList.remove('current');
                }
                event.target.classList.add('current');
                this.$emit('clicked-tag', tag);
                this.previous = event.target;
            }
        }
    }
}
</script>

<style scoped>
#tags{
    background: white;

}
#tags ul{
    display: flex;
    flex-flow: row wrap;
    justify-content: space-around;
    list-style: none;
    cursor: pointer;
}
#tags ul li {
    padding: 10px;
    font-family: Arial, Helvetica, sans-serif;
}
#tags ul li:last-child{
    background: black;
    color: white;
}
#tags ul li.current {
    transition: background 0.3s ease-in;
    background: #e4e4e4;
}
</style>