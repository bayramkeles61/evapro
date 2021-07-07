<template>
  <nav class="navbar">
    <label class="logo">DesignX</label>
    <ul class="menu">
      <li><nuxt-link to="/">Home</nuxt-link></li>
      <li><nuxt-link to="/">About</nuxt-link></li>
      <li><nuxt-link to="/">Services</nuxt-link></li>
      <li><nuxt-link to="/">Contact</nuxt-link></li>
      <li><nuxt-link to="/">About</nuxt-link></li>
    </ul>
  </nav>
</template>

<script>
export default {};
</script>

<style scoped>
.navbar {
  background: #0082e6;
  height: 60px;
  display: flex;
  justify-content: center;
  align-items: center;
}

.menu {
  display: flex;
  justify-content: center;
  align-items: center;

}

nuxt-link {
  color: var(--white);
  font-size: 17px;
  padding: 7px 13px;
  border-radius: 3px;
  text-transform: uppercase;
  text-decoration: none;

}

nuxt-link:active,
nuxt-link:hover {
  background: red;
  transition: 0.5s;
}
</style>
