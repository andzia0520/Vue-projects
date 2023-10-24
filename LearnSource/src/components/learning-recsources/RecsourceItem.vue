<template>
  <li>
    <div>
      <header>
        <h3>{{ title }}</h3>
        <button>Delete</button>
      </header>
    </div>
    <p>{{ description }}</p>
    <nav>
      <a :href="link">View Resource</a>
    </nav>
  </li>
</template>

<script>
export default {
  props: ['title', 'description', 'link'],
};
</script>

<style scoped>
li {
  margin: 0 auto;
  margin-bottom: 2em;
  height: 10rem;
  width: 40rem;
  list-style-type: none;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  border-radius: 15px;
}

div {
  margin: 0;
  padding: 0;
}

header {
  position: relative;
  margin: 0 10px;
  padding: 0;
}

h3 {
  display: inline-block;
  font-size: 1.3em;
  font-weight: bold;
  color: black;
}

button {
  position: absolute;
  right: 10px;
  top: 20px;
  padding: 1px;
  border: none;
  color: purple;
  background: none;
}

a {
  margin: 5px 10px;
  color: brown;
  text-decoration: none;
}
p {
  margin: 5px 10px;
  font-size: 1em;
}
</style>
