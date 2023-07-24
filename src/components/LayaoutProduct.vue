<script>
export default {
  props: {
    number: {
      type: Number,
      required: true,
    },
    product: {
      type: Object,
      required: true,
    },
  },
};

</script>

<template>
  <div class="aside-description">
    <img src="../assets/cafe.avif" alt="cafe">
    <div class="aside-description-reference">
      <span>#{{ number }} {{ product.name }}</span>
      <p>{{ product.clicks }} clicks</p>
    </div>
  </div>
</template>

<style scoped>

.aside-description {
    display: flex;
    width: auto;
    height: 45px;
    margin: 9px 10px 15px 20px;
    border-bottom: 1px solid rgb(231, 223, 223);
  }

  .aside-description-reference {
    margin-left: 10px;
  }

  .aside-description-reference p {
    margin-top: 5px;
  }
  .aside-description img {
    width: 40px;
    height: 40px;
    border-radius: 10px;
  }

  @media (max-width: 1180px),
  (max-height: 820px) {

    .aside-description {
    height: 47px;
    width: 200px;
  }

  .aside-description img {
    width: 35px;
    height: 35px;
  }
  .aside-description-reference p {
    margin: 0;
  }
  
  .aside-down-description-reference p {
    margin: 0;
  }
}

@media (max-width: 375px),
  (max-height: 667px) {
    .aside-up {
    margin: 15px 0;
    width: 325px;
  }

  .aside-down {
    margin: 15px 0;
    width: 325px;
  }
  
  .aside-description {
    width: 280px;
  }
}

</style>