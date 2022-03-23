<template>
  <div class="hello">
    <!-- Use the Prop passed into the component -->
    <h1>{{ msg }}</h1> 
    <h2>{{ msg2 }}</h2>
    <h1>Our Tests</h1>
    <!-- v-model will hold the data reference for storing input -->
    <input v-model="my_input">
    <p>Input value is: {{ my_input }}</p>
    <p> Lets access a key : {{ sample.key1 }}</p>

    <button @click="isVisible = !isVisible">Toggle</button>
    <!-- Can run logical statements using v-if and v-else  -->
    <div v-if="isVisible">Show content</div>
    <div v-else>Hide Content </div>

    <!-- Can run loops with v-for iterate through list data -->
    <ul v-for="(post, index) in posts" :key="index">
      <li>{{index}}. The name is {{post.name}} and the text is
          {{post.text}}
      </li>
    </ul>

  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  // Declare the expected values coming in
  props: {
    msg: String,
    msg2: String
  },
  data () {
    return {
      my_input : 'abc',
      sample : { key1: 'cde' },
      isVisible : true,
      posts: [{name: 'Jane', text: 'my text 1'}, {name:
            'John', text: 'my text 2'}]
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
