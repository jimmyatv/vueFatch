<template>
  <div class="fetch">
    <h1>USA universities</h1>
    <hr />
    <ul>
      <li v-for="(university, idx) in universities" :key="idx">
        <a href="">TEST{{ university.name }}</a>
      </li>
    </ul>
  </div>
</template>

//JS
<script>
export default {
  data() {
    return {
      universities: [],
    };
  },
  mounted() {
    fetch("http://universities.hipolabs.com/search?country=United+States")
      .then((res) => res.json())
      .then((uni) => {
        this.universities = uni;
      })
      .catch((error) => {
        console.error("Error fetching data:", error);
      });
  },
};
</script>

//CSS
<style scoped>
.fetch li {
  list-style: none;
}
</style>