<script>
import LayaoutProduct from './LayaoutProduct.vue';

export default {
  components: {
    LayaoutProduct,
  },
  data() {
    return {
      productList: [
        {name: 'Product 1', clicks: 120 },
        {name: 'Product 2', clicks: 120 },
        {name: 'Product 3', clicks: 120 },
        {name: 'Product 4', clicks: 120 },
        {name: 'Product 5', clicks: 120 },
      ],
    };
  },
};
</script>

<template>
    <main>
      <p>Dashboard</p>
      <div class="main-box"> 
      <section>
        <p class="sessions">Total sessions</p>
        <div class="main-nav">
          <div class="main-nav-date">
            <button class="button-left">Monthly</button>
            <button class="button-right">Weekly</button>
            <a href="">Today</a>
          </div>
        </div>
  
        <div class="main-container">
          <p>graphic</p>
          <p class="main-container-sessions">Total sessions</p>
          <p class="main-container-time">Month/Day/Hour</p>
        </div>
  
      </section>
  
      <aside>
        <div class="aside-up">
           <div class="aside-up-information">
              <div class="aside-up-information-title">
                <p>Most clicked</p>
                <span>Last 30 days</span> 
              </div>
              <LayaoutProduct v-for="(product, index) in productList" :key="index" :number="index + 1" :product="product" />
          </div>
        </div>
        <div class="aside-down">
          <div class="aside-down-information">
              <div class="aside-down-information-title">
                <p>Less clicked</p>
                <span>Last 30 days</span> 
            </div>
              <LayaoutProduct v-for="(product, index) in productList" :key="index" :number="index + 1" :product="product" />
          </div>
        </div>
      </aside>
    </div>
  </main>
  </template>

<style>

  #app {
    overflow-x: hidden;
  }

  main {
    display: flex;
    flex-direction: column;
    width: 100%;
    height: 100vh;
    background-color: #fbfbfb;
    padding: 10px;
    overflow: hidden;
  }

  .main-box {
    display: flex;
    justify-content: space-around;
    align-items: center;
  }

  section {
    width: 70%;
    height: 90vh;
    background-color: white;
    border-radius: 10px;
    position: relative;
    border: 1px solid rgb(224, 219, 219);
  }

  .sessions {
    position: absolute;
    top: 15px;
    left: 15px;
    margin: 0;
  }

  .main-nav {
    display: flex;
    justify-content: end;
    width: 85%;
    margin: 15px auto;
  }

  .main-nav-date {
    display: flex;
    align-items: center;
    justify-content: center;
  }

  .main-nav-date button {
    margin: 0 5px;
  }

  .button-left {
    height: 40px;
    width: 80px;
    background-color: #4835bb;
    color: white;
    border: none;
    border-radius: 5px;
  }

  .button-right {
    height: 40px;
    width: 80px;
    color:  #4835bb;
    background-color: white;
    border: 1px solid  #4835bb;
    border-radius: 5px;
  }

  .main-nav-date a {
    margin: 0 0 0 15px;
    text-decoration: none;
    color: #4835bb;
  }

  .main-container {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 85%;
    height: 75vh;
    margin: 0 auto;
    background-color: #ebebeb;
    position: relative;
  }

  .main-container-sessions {
    position: absolute;
    left: -80px; 
    top: 50%; 
    transform: translateY(-50%) rotate(-90deg);
    margin: 0;
  }

  .main-container-time {
    position: absolute;
    bottom: -50px; 
    left: 50%; 
    transform: translateX(-50%); 
    margin: 0;
  }

  aside {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
  }

  .aside-up {
    width: 320px;
    height: cover;
    background-color: white;
    border-radius: 20px;
    border: 1px solid rgb(230, 224, 224);
    margin-bottom: 5px;
  }

  .aside-up-information {
    display: flex;
    flex-direction: column;
  }

  .aside-up-information-title {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 0 20px;
  }

  .aside-up-information-title span {
    text-align: center;
    width: 110px;
    height: 20px;
    color: white;
    background-color: #4835bb;
    border-radius: 10px;
  }

  .aside-up-information-title p {
    color: gray;
  }

  .aside-down {
    width: 320px;
    height: cover;
    background-color: white;
    border-radius: 20px;
    border: 1px solid rgb(230, 224, 224);
    margin-bottom: 5px;
  }

  .aside-down-information {
    display: flex;
    flex-direction: column;
  }

  .aside-down-information-title {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 0 20px;
  }

  .aside-down-information-title span {
    text-align: center;
    width: 110px;
    height: 20px;
    color: white;
    background-color: #4835bb;
    border-radius: 10px;
  }

  .aside-down-information-title p {
    color: gray;
  }


  @media (max-width: 1180px),
  (max-height: 820px) {

  section {
    width: 47%; 
    height: 50vh; 
  }

  .main-box {
    display: flex;
    justify-content: space-between;
  }

  .main-container {
    height: 35vh;
  }

  .main-container-sessions {
    left: -70px; 
  }

  .main-container-time {
    bottom: -40px; 
  }

  aside {
    flex-direction: row;
  }

  .aside-up {
    width: 270px;
    margin: 0 10px 0 0;
  }

  .aside-down {
    width: 270px;
    margin: 0 25px 0 10px;
  }


}

@media (max-width: 375px),
  (max-height: 667px) {
    
  section {
    width: 90%;
    height: 85vh;
    margin: 0 auto;
  }

  main {
    padding: 0;
    overflow: auto;
  }

  .main-box {
      flex-direction: column;
    }
  
  .main-nav {
    justify-content: start;
    margin: 40px 0 25px 20px;
  }

  .main-container {
    height: 60vh;
    width: 70%;
  }

  aside {
    flex-direction: column;
  }

  .aside-up {
    margin: 15px 0;
    width: 325px;
  }

  .aside-down {
    margin: 15px 0;
    width: 325px;
  }
}

  </style>