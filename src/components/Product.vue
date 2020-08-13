<!-- Since I'm only grabbing 1 product from the API call,
 I made 1 singular component but if I had multiple products I would break it down into a Products and Product component-->
<template>
  <div class="product-container">
    <h2>Black Valentino dress with tulle</h2>

    <div class="tags-container">
      <span class="popular">Popular</span>
      <img class="favorite" src="../assets/iconFavourite.svg" />
    </div>
    <!--.tags-->

    <div class="rating-container">
      <ul class="star-rating">
        <li>
          <img src="../assets/iconActiveStar.svg" />
        </li>
        <li>
          <img src="../assets/iconActiveStar.svg" />
        </li>
        <li>
          <img src="../assets/iconActiveStar.svg" />
        </li>
        <li>
          <img src="../assets/iconActiveStar.svg" />
        </li>
        <li>
          <img src="../assets/iconActiveStar.svg" />
        </li>
      </ul>
      <span class="number-rating">132 reviews</span>
    </div>
    <!--.rating-->

    <div class="info-container">
      <div class="product-info"></div>
      <div class="product-brand"></div>
      <div class="product-delivery"></div>
    </div>
    <!--.info-->

    <div class="options-container">
      <div class="size">
        <h3>Size</h3>
        <span>Size Guide</span>
        <button>XS</button>
        <button>S</button>
        <button>M</button>
      </div>
      <div class="color">
        <h3>Color</h3>
        <button></button>
        <button></button>
        <button></button>
      </div>
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
      products: [],
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
          this.products.push(response.data);
        } else {
          console.log("Something went wrong. 😒");
        }
      });
  },
};
</script>

<style>
</style>