<!-- Since I'm only grabbing 1 product from the API call,
 I made 1 singular component but if I had multiple products I would break it down into a Products and Product component-->
<template>
  <div class="product-container">
    <h2> {{product[0].title ? product[0].title : 'No title found'}} </h2>

    <div class="tags-container">
      <span class="popular" v-bind:key="tag.id" v-for="tag in product[0].tags">{{tag}}</span>
      <img class="favorite" src="../assets/iconFavourite.svg" />
    </div>
    <!--.tags-->

    <div class="rating-container">
      <ul class="star-rating">
        <li v-bind:key="rating.id" v-for="rating in product[0].average_rating">
          <img src="../assets/iconActiveStar.svg" />
        </li>
      </ul>
      <span class="number-rating">{{product[0].number_of_reviews}}</span>
    </div>
    <!--.rating-->

    <div class="info-container">
      <div class="product-info">{{product[0].info}}</div>
      <div class="product-brand">{{product[0].brand}}</div>
      <div class="product-delivery">{{product[0].delivery}}</div>
    </div>
    <!--.info-->

    <div class="options-container">
      <div class="size">
        <h3>Sizes</h3>
        <span>Size Guide</span>
        <div class="sizes" v-bind:key="size.id" v-for="size in product[0].sizes"><button>{{size}}</button></div>
      </div>

      <div class="color" v-bind:key="color.id" v-for="color in product[0].colors"><button>{{color}}</button></div>
    </div>
    <!--.options-->

    <div class="cart-container">
      <span>$788</span>
      <button>Add To Cart</button>
    </div>
    <!--.cart-->
  </div>
</template>

<script>
import axios from "axios";
export default {
  /*using axios to make first api call for auth token and then another api call for the test data using the auth token*/
  data() {
    return {
      product: [], //not necessary to use an array here but would make sense if we had multiple products
    };
  },
  mounted() {
    axios
      .post("https://api.getrunner.io/runner/v4/login", {
        data: {
          type: "login credentials",
          attributes: {
            email: "negin@getrunner.io",
            password: "secret",
            anonymousId: "34234234",
          },
        },
      })
      .then((response) => response.data.data.attributes.accessToken)
      .then((token) =>
        axios.get("https://api.getrunner.io/runner/v4/code-test-product", {
          params: {},
          headers: { Authorization: `Bearer ${token}` },
        })
      )
      .then((response) => {
        if (response) {
          this.product.push(response.data);
          console.log(this.product)
        } else {
          console.log("Something went wrong. 😒");
        }
      });
  },
};
</script>

<style>
</style>