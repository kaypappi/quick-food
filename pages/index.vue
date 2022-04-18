<template>
  <div class="landing-wrapper">
    <section id="hero" class="hero position-relative">
      <nav-bar class="fixed-top" />
      <div class="container h-100">
        <div class="hero-content row h-100">
          <div
            class="
              col-md-7
              left-content
              d-flex
              flex-column
              justify-content-center
              h-100
              position-relative
            "
          >
            <div>
              <span class="h1 text-white lh-lg manrope font-weight-bolder"
                >Your favorite food, </span
              ><br />
              <span class="h1 text-white manrope font-weight-bolder"
                >delivered</span
              >
              <span class="h1 text-lemon-500 manrope font-weight-bolder"
                >fast and fresh</span
              >
            </div>
            <p class="h6 text-white lh-md manrope hero-caption mt-4">
              With our integrated CRM, project management, collaboration and
              invoicing capabilities, you can manage every aspect of your
              business in one secure platform.
            </p>
            <custom-input
              name="first Name"
              type="text"
              label="First Name"
              style="maxWidth: 400px"
              class="mb-2 mt-4 dmsans"
              placeholder="Enter your location"
            >
              <template v-slot:right-slot>
                <button class="btn bg-white py-1 px-3 text-white">
                  <icon-base width="30px" height="30px" icon="fold" />
                </button>
              </template>
            </custom-input>
            <div class="d-flex align-items-center">
              <icon-base width="20px" height="20px" icon="green-check" />
              <p class="h6 ml-2 mb-0 manrope text-white">
                Save location for next time
              </p>
            </div>
          </div>
          <div class="col-md-5 position-relative">
            <div class="right-content">
              <img src="/images/hero1.png" alt="" class="hero1" />
              <img src="/images/hero-sqiggle.png" alt="" class="hero-sqiggle" />
            </div>
          </div>
        </div>
      </div>
    </section>
    <section class="restuarants-info bg-cream-500 py-5">
      <div class="container">
        <h4 class="h4 font-weight-bolder text-gray-900">
          What do you want to eat?
        </h4>
        <p class="h6 mb-0 text-gray-500">
          Enter your location and choose the type of food you want
        </p>
        <div class="row mx-md-n4 mt-5 pt-5">
          <div class="col-md-4 px-md-4">
            <meals-category-cards />
          </div>
          <div class="col-md-4 px-md-4">
            <meals-category-cards />
          </div>
          <div class="col-md-4 px-md-4">
            <meals-category-cards />
          </div>
        </div>
        <div
          class="
            separator
            d-flex
            my-4
            justify-content-center
            align-items-center
          "
        >
          <hr style="width: 100px" class="bg-gray-100 m-0" />
          <h6 class="text-gray-500 h6 mb-0 mx-2">Or</h6>
          <hr style="width: 100px" class="bg-gray-100 m-0" />
        </div>
        <custom-input
          name="first Name"
          type="text"
          label="First Name"
          style="maxWidth: 500px"
          class="mb-2 mt-4 ml-auto mr-auto dmsans"
          placeholder="Enter your location"
          bordered
        >
          <template v-slot:right-slot>
            <button class="btn bg-orange-500 py-2 px-4 text-white">
             Search
            </button>
          </template>
        </custom-input>
        <h6 class="h6 text-center manrope">Your location helps us locate the closest outlet to you</h6>
      </div>
    </section>
  </div>
</template>

<script>
import NavBar from '@/components/NavBar.vue'
import CustomInput from '~/components/CustomInput.vue'
import IconBase from '@/components/IconBase.vue'
import MealsCategoryCards from '@/components/Cards/MealsCategoryCards.vue'
export default {
  name: 'IndexPage',
  components: {
    NavBar,
    CustomInput,
    IconBase,
    MealsCategoryCards,
  },
}
</script>

<style scoped>
.hero {
  background: linear-gradient(45deg, #02a486 0%, #00525b 100%);
  height: 50vh;
}
.hero-caption {
  max-width: 500px;
}
.swirl {
  position: absolute;
  top: 0;
  left: 0;
  z-index: 0;
}
.right-content {
  position: absolute;
  bottom: -100px;
  left: 0;
}
.left-content {
  background-image: url('/images/swirls.png');
  background-position: 70% 50px;
  background-repeat: no-repeat;
}
.hero-sqiggle {
  position: absolute;
  left: -60%;
  bottom: 0px;
  height: 60%;
}
.hero1 {
  height: 350px;
}
</style>
