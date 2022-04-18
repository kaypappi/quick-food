<template>
  <div class="navbar-wrapper container">
    <b-navbar variant="transparent" toggleable="lg" class="px-0 py-4" type="dark" >
      <b-navbar-brand href="#"><img src="/svgs/logo.svg" alt=""></b-navbar-brand>

      <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

      <b-collapse id="nav-collapse" is-nav>

        <!-- Right aligned nav items -->
        <b-navbar-nav class="ml-auto">
          <b-nav-form>
            <button size="sm" class="my-2 my-sm-0 btn btn--transparent text-white" type="submit"
              >Log In</button
            >
            <button size="sm" class="my-2 my-sm-0 px-3 py-2 btn bg-sea-green-600 text-white" type="submit"
              >Sign Up</button
            >
          </b-nav-form>

         <!--  <b-nav-item-dropdown text="Lang" right>
            <b-dropdown-item href="#">EN</b-dropdown-item>
            <b-dropdown-item href="#">ES</b-dropdown-item>
            <b-dropdown-item href="#">RU</b-dropdown-item>
            <b-dropdown-item href="#">FA</b-dropdown-item>
          </b-nav-item-dropdown>

          <b-nav-item-dropdown right>
            <template #button-content>
              <em>User</em>
            </template>
            <b-dropdown-item href="#">Profile</b-dropdown-item>
            <b-dropdown-item href="#">Sign Out</b-dropdown-item>
          </b-nav-item-dropdown> -->
        </b-navbar-nav>
      </b-collapse>
    </b-navbar>
  </div>
</template>

<script>

export default {
    components:{
        
    }
}
</script>

<style>
</style>