<script setup>
import { RouterLink, RouterView } from 'vue-router'
import page1 from '@/components/page1.vue'
import page2 from '@/components/page2.vue'
import page3 from '@/components/page3.vue'
</script>

<template>
  <div class="container">
    <header>
      <h1>Header</h1>
      <nav>
        <ul>
          <li>
            <RouterLink to="/page1" active-class="active-link">Page 1</RouterLink>
          </li>
          <li>
            <RouterLink to="/page2" active-class="active-link">Page 2</RouterLink>
          </li>
          <li>
            <RouterLink to="/page3" active-class="active-link">Page 3</RouterLink>
          </li>
        </ul>
      </nav>
    </header>

    <main>
      <div class="menu">
        <h2>Menu</h2>
        <ul>
          <li><RouterLink to="/section1" active-class="active-link">Section 1</RouterLink></li>
          <li><RouterLink to="/section2" active-class="active-link">Section 2</RouterLink></li>
          <li><RouterLink to="/section3" active-class="active-link">Section 3</RouterLink></li>
          <li><RouterLink to="/section4" active-class="active-link">Section 4</RouterLink></li>
        </ul>
      </div>

      <div class="content">
        <RouterView />
      </div>
    </main>

    <footer>
      <h1>Footer</h1>
    </footer>
  </div>
</template>

<style>
.container {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
  width: 1250px;
}

header {
  background-color: #f0f0f0;
  padding: 20px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

nav ul {
  list-style-type: none;
  padding: 0;
  margin: 0;
  display: flex;
}

nav li {
  display: inline-block;
  margin-right: 20px;
}

nav a {
  color: black; /* Default link color */
}

.active-link {
  color: red; /* Active link color */
}

main {
  flex: 1;
  display: flex;
}

.menu {
  width: 400px;
  background-color: #f0f0f0;
  padding: 20px;
}

.content {
  flex: 1;
  padding: 20px;
  background-color: #f0f0f0;
}

footer {
  background-color: #f0f0f0;
  padding: 20px;
  text-align: center;
}
</style>