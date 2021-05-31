<template>
<div class="container">
<nav class="navbar navbar-expand-lg navbar-light bg-light">
  <router-link class="navbar-brand text-style" to="/"> Flask and Vue3</router-link>
  <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
    <span class="navbar-toggler-icon"></span>
  </button>

  <div class="collapse navbar-collapse" id="navbarSupportedContent">
    <ul class="navbar-nav ms-auto">
      <li class="nav-item active">
        <router-link class="btn btn-primary" to="/">Home</router-link>
      </li>
      <li class="nav-item">
        <router-link class="btn btn-success" to="/create">Create</router-link>
      </li>
      <li class="nav-item">
        <router-link class="btn btn-danger" to="/create">Delete</router-link>
      </li>
    </ul>
  </div>
</nav>
</div>

</template>

<script>
export default {

}
</script>

<style>
.text-style {
  font-size: 30px !important;
  font-family: fantasy !important;
  color: brown !important
}
</style>