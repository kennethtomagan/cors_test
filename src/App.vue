<template>
  <div id="app">
    <h1 class="title">Felix CORS TEST</h1>
    <div class="container">
        <label for="url"><b>Enter URL</b></label>
        <input type="text" id="url" name="url" placeholder="URL" v-model="data.url">
        <button type="submit"  @click="submit">Submit</button>
    </div>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
// import Vue from "vue";
export default {
    name: 'App',
    data() {
        return {
            data: {
                url: null
            }
        };
    },
    methods: {
        submit() {
        this.$axios
            .get(this.data.url)
            .then(response => {
                console.log(response);
            }).catch(error=>{
                console.log(error.response)
            });
        }
    }
}
</script>

<style>
.title{
    text-align: center;
}
body {font-family: Arial, Helvetica, sans-serif;}
form {border: 3px solid #f1f1f1;}

input[type=text], input[type=password] {
  width: 100%;
  padding: 12px 20px;
  margin: 8px 0;
  display: inline-block;
  border: 1px solid #ccc;
  box-sizing: border-box;
}

button {
  background-color: #04AA6D;
  color: white;
  padding: 14px 20px;
  margin: 8px 0;
  border: none;
  cursor: pointer;
  width: 100%;
}

button:hover {
  opacity: 0.8;
}


img.avatar {
  width: 40%;
  border-radius: 50%;
}

.container {
    padding: 16px;
    width: 60%;
    margin: auto;
}

/* Change styles for span and cancel button on extra small screens */
@media screen and (max-width: 300px) {
    .container {
        width: 100%;
        margin: auto;
    }
}
</style>
