<template>
  <nav>
    <router-link to="/">Home</router-link> |
    <router-link to="/report">Report</router-link>
  </nav>
  <router-view/>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;

  min-height: 100vh;
  background: #F5F9FF;  
}

:root {
  --primary-color-500: #0BA5EC;
  --primary-color-700: #0086c9;

  --secondary-color-300: #AFB5D9;
  --secondary-color-400: #717bbc;

  --input-color: #99A3BA;
  --input-border: #CDD9ED;
  --input-background: #fff;
  --input-placeholder: #CBD1DC;
  
  --input-border-focus: #275EFE;
  
  --group-color: var(--input-color);
  --group-border: var(--input-border);
  --group-background: #EEF4FF;
  
  --group-color-focus: #fff;
  --group-border-focus: var(--input-border-focus);
  --group-background-focus: #678EFE;
}

nav {
  padding: 0px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #42b983;
}

input[type=text] {
  display: block;
  padding: 4px 8px;
  font-size: 14px;
  font-weight: 500;
  font-family: inherit;
  border-radius: 6px;
  -webkit-appearance: none;
  color: var(--input-color);
  border: 1px solid var(--input-border);
  background: var(--input-background);
  transition: border .3s ease;
  &::placeholder {
      color: var(--input-placeholder);
  }
  &:focus {
      outline: none;
      border-color: var(--input-border-focus);
  }
}

button {
  background-color: var(--primary-color-500);
  border: none;
  color: white;
  padding: 8px 12px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  margin: 2px 10px;
  border-radius: 4px;
  transition-duration: 0.4s;
}

button:hover {
  background-color: var(--primary-color-700);
  color: white;
}

</style>
