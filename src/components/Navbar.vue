
<template>
  <div class="navbar">
    <div class="container">
      <nav>
        <div class="logo">
          <h1>youtube api</h1>
        </div>
      </nav>
    </div>
  </div>
</template>

<script>
export default {
 name: 'Navbar',

}
</script>

<style>
  .navbar {
    display: flex;
    align-items: center;
    height: 60px;
    background: crimson;
  }

  .logo h1 {
    text-transform: uppercase;
    color: #fff
  }

</style>