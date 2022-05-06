<template>
  <header>
    <nav class="navbar navbar-dark bg_color_dark_side">
      <div class="container-fluid">
        <a class="navbar-brand" href="#">
          <img src="@/assets/spotify.png" alt="" height="50" width="50" />
        </a>
        
          <form class="d-flex">
            <input
              class="form-control me-2"
              type="search"
              placeholder="Search"
              aria-label="Search"
            />
            <button class="btn btn-outline-success" type="submit">
              Search
            </button>
          </form>
        </div>
      
    </nav>
  </header>
</template>

<script>
export default {
  name: "SiteHeader",
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">
@import "@/assets/scss/style.scss";
</style>