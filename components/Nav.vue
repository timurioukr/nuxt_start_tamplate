<template>
  <nav class="navbar navbar-expand-lg navbar-dark bg-dark padding">
    <NuxtLink class="navbar-brand" to="/">Find worker</NuxtLink>
    <button
      class="navbar-toggler"
      type="button"
      data-toggle="collapse"
      data-target="#navbarSupportedContent"
      aria-controls="navbarSupportedContent"
      aria-expanded="false"
      aria-label="Toggle navigation"
    >
      <span class="navbar-toggler-icon"></span>
    </button>

    <div class="collapse navbar-collapse ml-auto" id="navbarSupportedContent">
      <ul class="navbar-nav ml-auto">
        <li class="nav-item active">
          <NuxtLink to="/users" class="nav-link"
            >Workers</NuxtLink
          >
        </li>
        <li class="nav-item active">
          <NuxtLink to="/my-workers" class="nav-link"
            >My workers</NuxtLink
          >
        </li>
      </ul>
    </div>
  </nav>
</template>

<script>
export default {};
</script>

<style scoped>
    .padding {
        padding: 10px;
        background-color: black
    }
    .nav-left {
        margin-left: auto;
    }
</style>
