<script setup>
  import {RouterLink} from "vue-router";

  defineProps({
      list: Array,
  });
</script>

<template>
  <div class="drop-down-container">
    <div class="drop-down-btn">
      <slot/>
    </div>
    <div class="drop-down-menu" v-if="list">
      <ul>
        <li v-for="{name, url} in list">
          <RouterLink class="no-link-style" :to="url">{{name}}</RouterLink>
        </li>
      </ul>
    </div>
  </div>
</template>

<style scoped>
.drop-down-container {
  position: relative;
}

.drop-down-btn {
  padding: 0.5rem 1rem;
  margin: 0;
  width: 5.3rem;
  display: inline-block;
  cursor: pointer;
  font-size: 1rem;
  font-weight: bold;
  color: white;
  text-align: left;
  border-radius: 2rem;
}

.drop-down-container:hover .drop-down-btn {
  background-color: #272030;
}

.drop-down-container:hover .drop-down-menu {
  display: inline-block;
}

.drop-down-menu {
  position: absolute;
  display: none;
  margin: 0;
  padding-left: 0.5rem;
}

.drop-down-menu ul {
  width: 8rem;
  background-color: #272030;
  border-radius: 1.1rem;
  margin: 0;
  padding: 0.1rem 0.5rem 0.1rem 2.5rem;
}

.drop-down-menu li {
  margin: 0.8rem 0;
  color: white;
  text-indent: 0.5rem;
}

.drop-down-menu li:hover {
  text-decoration-line: underline;
}

.drop-down-menu li * {
  color: white;
  font-size: 0.8rem;
}

</style>