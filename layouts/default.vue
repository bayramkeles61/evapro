<template>
  <div>
    <TheHeader />
    <main class="main-content">
      <Nuxt />
      <TheIcons />
    </main>
  </div>
</template>

<script>
import TheHeader from "~/components/Header/TheHeader.vue";
import TheIcons from "~/components/Icons/TheIcons.vue";

export default {
  components: {
    TheHeader,
    TheIcons
  }
};
</script>

<style>
:root {
  --blue: #63b3ed;
  --blue-dark: #445573;
  --blue-special: #238ecf;
  --indigo: #596cff;
  --purple: #7986cb;
  --purple-dark: #303f9f;
  --pink: #d63384;
  --red: #f56565;
  --orange: #fd7e14;
  --yellow: #fbd38d;
  --green: #81e6d9;
  --green-dark: #00796b;
  --teal: #20c997;
  --cyan: #0dcaf0;
  --cyan-dark: #0097a7;
  --gray-shadow: #ebeff3;
  --gray-light: #dee2e6;
  --gray: #6c757d;
  --gray-dark: #343a40;
  --primary: #cb0c9f;
  --secondary: #8392ab;
  --success: #82d616;
  --info: #17c1e8;
  --warning: #f53939;
  --danger: #ea0606;
  --light: #f8f9fa;
  --dark: #252f40;
  --white: #fff;
  --font-sans-serif: "Open Sans";
  --font-monospace: SFMono-Regular, Menlo, Monaco, Consolas, "Liberation Mono",
    "Courier New", monospace;
  --gradient: linear-gradient(
    180deg,
    hsla(0, 0%, 100%, 0.15),
    hsla(0, 0%, 100%, 0)
  );
}

*,
*::before,
*::after {
  outline: 0;
  box-sizing: border-box;
  margin: 0;
  padding: 0;
  border: 0;
  text-decoration: none;
  text-shadow: none;
}

html {
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
  width: 100%;
  height: 100%;
  font-size: 100%;
  word-spacing: 1px;
}

body {
  background-color: var(--light);
  margin: 0;
  padding: 0;
  font-family: var(--font-sans-serif);
  overflow: scroll;
}

a {
  text-decoration: none;
}

.main-content {
  padding-top: 4.5rem;
}
</style>
