<template>
    <div class="container">
      <header>
        <h1>Header</h1>
        <nav>
          <ul>
            <li><RouterLink to="/">Home</RouterLink></li>
            <li><RouterLink to="/page1">Page 1</RouterLink></li>
            <li><RouterLink to="/page2">Page 2</RouterLink></li>
            <li><RouterLink to="/page3">Page 3</RouterLink></li>
          </ul>
        </nav>
      </header>
  
      <main>
        <RouterView />
      </main>
  
      <footer>
        <h1>Footer</h1>
      </footer>
    </div>
  </template>
  
  <script>
  import { RouterLink, RouterView } from 'vue-router';
  
  export default {
    components: {
      RouterLink,
      RouterView,
    },
  };
  </script>