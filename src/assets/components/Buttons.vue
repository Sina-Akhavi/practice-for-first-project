<template>
  {{ greetingMessage }}
  <div class="navbar">
    <button @click="$emit('showOne')" class="show-btn">Show</button>
    <button @click="$emit('hideOne')" class="hide-btn">Hide</button>
  </div>
</template>

<script>
  export default {
    emits: ['showOne', 'hideOne'],
    props: ['greetingMessage']

  }
</script>


<style>

button.show-btn, button.hide-btn {
  width: 8%;
  height: 4em;
  border-radius: 5px;
  font-weight: bolder;
  font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
}

.show-btn {
  background-color: green;
}

.hide-btn {
  background-color: red;
  float: right;
}

.navbar {
  margin-bottom: 15px;
}

</style>