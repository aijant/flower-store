<template>
  <div class="features">
    <div class="container">
      <h4 class="features-title">{{ content.title }}</h4>
      <div class="function">
        <div class="item" v-for="item in content.logos" :key="item.id">
          <img :src="item.img"/>          
          <div class="design">
            <h3 class="brand"> {{ item.brand }}</h3>
            <p class="product">{{ item.product }}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import languageHelper from "../languages/langhelper.js"
export default {
  name: 'Features',
   created(){
     this.setContent(languageHelper.getFeaturesContent(this.language))
  },
  data(){
    return {
      content: {}          
    }
  },
   methods:{
    setContent(data){
      this.content = data
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .features {
    background-color: #3a454d;
  }
  .container {
    width: 1250px;
    margin: 0 auto;
  }

  .features-title {
    text-align: left;
    padding-left: 18px;
    border-left: 5px solid #e1e6ea;
    color:#e1e6ea;
    font-size: 18px;
    margin-left: 55px;
    line-height: 42px;
    text-transform: uppercase;
  }

  .function {
    display: flex;
    flex-wrap: wrap;
  }

  .item {
    padding: 15px;
    width: 383px;
  }

  .item:last-child {
    padding-right: 0;
  }

  .brand {
    color: #ffffff;
    font-size: 18px;
    line-height: 42px;
    text-transform: uppercase;
  }

  .product {
    color: #dcdfe1;
    font-size: 16px;
    line-height: 26px; 
  }

  @media screen and (max-width: 1100px){
    .container {
      width: 1100px; 
    }
  }

  @media screen and (max-width: 825px){
    .container {
      width: 800px; 
    }
  }

  @media screen and (max-width: 442px){
    .container {
      width: 419px; 
    }
  }

</style>
