<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <h2>How I Built This Page</h2>
    <p>
      To install Vue CLI, I ran the command
      <code>npm install -g @vue/cli</code>. Then, I created a new project using
      <code>vue create my-vue-project</code>.
    </p>

    <h2>Building the Page</h2>
    <p>
      I modified the <code>HelloWorld.vue</code> component to include this
      content. I used Vue's templating syntax to structure the HTML and added
      some basic CSS for styling.
    </p>

    <h2>Difficulties Encountered</h2>
    <p>
      One difficulty I encountered was configuring the project to work with
      GitHub Pages. I solved this by following the official Vue documentation on
      deploying to GitHub Pages.
    </p>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },
};
</script>

<style scoped>
.hello {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: left;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
