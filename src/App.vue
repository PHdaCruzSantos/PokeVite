<script setup>
</script>

<template>
  <nav class="navbar navbar-expand-lg navbar-dark bg-primary">
    <div class="container-fluid">
      <router-link class="navbar-brand" to="/">
        <img
          src="http://cdn-icons-png.flaticon.com/512/188/188987.png"
          alt="Logo"
          width="30"
          height="24"
          class="d-inline-block align-text-top"
        />
        <router-link class="navbar-brand flex" to="/">PokeVite</router-link>
      </router-link>
      <button
        class="navbar-toggler"
        type="button"
        data-bs-toggle="collapse"
        data-bs-target="#navbarNav"
        aria-controls="navbarNav"
        aria-expanded="false"
        aria-label="Toggle navigation"
      >
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarNav">
        <ul class="navbar-nav">
          <li class="nav-item">
            <router-link class="nav-link" aria-current="page" to="/"
              >Home</router-link
            >
          </li>
          <li class="nav-item">
            <router-link class="nav-link" to="/about">About</router-link>
          </li>
        </ul>
      </div>
    </div>
  </nav>

  <div class="main">
    <router-view></router-view>
  </div>

  <footer class="bg-primary text-light">
    <div>&copy; {{ new Date().getFullYear() }}</div>
  </footer>
</template>

<style>
footer {
  position: relative;
  top: 75px;
  bottom: 0;
  width: 100%;
  height: 56px;
  display: flex;
  align-items: center;
  justify-content: center;
}
</style>
