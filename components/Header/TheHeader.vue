<template>
  <header class="main-header">
    <nav class="main-nav">
      <div class="nav-logo">
        <svg class="logo-svg">
          <use href="#startup-1" />
        </svg>
        <span class="logo"
          ><nuxt-link to="/">
            eva<span class="logo-part">pro</span></nuxt-link
          ></span
        >
      </div>
      <div class="nav-menu">
        <ul class="menu-links">
          <nuxt-link to="/" class="menu-link">Anasayfa</nuxt-link>
          <li>
            <nuxt-link to="/companies" class="menu-link">Şirketler</nuxt-link>
          </li>
          <li>
            <nuxt-link to="/projects" class="menu-link">Projeler</nuxt-link>
          </li>
          <li>
            <nuxt-link to="/juries" class="menu-link">Jüriler</nuxt-link>
          </li>
           <li>
            <nuxt-link to="/evaluations" class="menu-link"
              >Değerlendirmeler</nuxt-link
            >
          </li>
          <li>
            <nuxt-link to="/about" class="menu-link">Hakkında</nuxt-link>
          </li>
        </ul>
      </div>
      <div class="nav-profile">
        <img
          src="~/assets/images/profile.jpg"
          alt="profile"
          class="profile-picture"
        />
        <div class="profile-text-container">
          <span>Mehmet Emin</span>
          <svg class="profile-arrow">
            <use href="#down-arrow" />
          </svg>
        </div>
      </div>
    </nav>
  </header>
</template>

<script>
export default {
  components: {}
};
</script>

<style scoped>
.main-header {
  position: fixed;
  top: 0;
  left: 0;
  height: 4.5rem;
  width: 100%;
  background-color: var(--white);
}

.main-nav {
  background-color: var(--blue-special);
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  box-shadow: rgba(0, 0, 0, 0.2) 0px 12px 28px 0px,
    rgba(0, 0, 0, 0.1) 0px 2px 4px 0px,
    rgba(255, 255, 255, 0.05) 0px 0px 0px 1px inset;
}

.nav-logo {
  color: var(--white);
  display: flex;
  justify-content: center;
  align-items: center;
  margin: auto;
  flex: 2;
}

.logo-svg {
  width: 52px;
  height: 52px;
  padding-right: 10px;
}

.logo {
  font-size: 2rem;
  font-weight: 700;
}

.logo-part {
  color: var(--orange);
  text-shadow: 2;
}

.nav-menu {
  flex: 5;
}

.menu-links {
  font-size: 16px;
  font-weight: 700;
  letter-spacing: 1px;
  color: var(--dar);
  list-style: none;
  margin: 0;
  padding: 0;
  height: 100%;

  display: flex;
  justify-content: center;
  align-items: center;
}

.menu-link {
  height: 100%;

  display: flex;
  justify-content: center;
  align-items: center;
  margin: 0 1rem;
  padding: 0.3rem;
  text-decoration: none;
  color: var(--white);
}

.menu-link:hover {
  color: var(--orange);
}

.nuxt-link-active {
  color: var(--white);
}

.nuxt-link-exact-active {
  color: var(--white);
}

.nav-profile {
  color: var(--light-text);
  height: 100%;

  display: flex;
  justify-content: center;
  align-items: center;
  flex: 2;
}

.profile-picture {
  padding: 10px;
  height: 55px;
  width: 55px;
  border-radius: 30px;
  object-fit: cover;
}

.profile-text-container {
  font-size: 14px;
  font-weight: 500;
  letter-spacing: 1px;
  color: var(--white);
}

.profile-text {
  margin: 0px 20px;
}

.profile-arrow {
  height: 12px;
  width: 12px;
  fill: var(--light);
}
</style>
