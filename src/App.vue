<script>
  export default {
    data() {
      return {
        people: [
          {name: "Sina", expl:"I am 20 years old"},
          {name: "Hossein", expl:"I am 21 years old"},
          {name: "Ali", expl:"I am 22 years old"},
          {name: "Reza", expl:"I am 23 years old"},
        ],

        index: 0,

        newName: '',
        explanation: ''
      }

    },

    methods: {
      showOne() {
        if (this.index > this.people.length - 1) {
          alert(`index = ${this.index} is the maximum`);
          return;
        } 
        this.index += 1;
      },

      disappearOne() {
        if (this.index <= 0) {
          alert(`index = ${this.index} is the minimum`);
          return;
        } 
        this.index -= 1;
      },

      submit() {
        if (!this.newName || !this.explanation) {
          alert('Can not be empty!!!');
          return;
        }
        const newPerson = {name: this.newName, expl:this.explanation} ;
        this.people.push(newPerson);

        this.newName = '';
        this.explanation = '';
      }
    }
  }
</script>

<template>
  <div class="navbar">
    <button @click="showOne" class="show-btn">Show</button>
    <button @click="disappearOne" class="hide-btn">Hide</button>
  </div>


    <template v-for="(person, i) in people">
      <p v-if="i < index" class="bording">
        {{ person.name }}
        <small class="smallEl">{{ person.expl }}</small>
      </p>
      
    </template>

    


    <div>
      <label for="new-person">Enter name: </label>
      <input type="text" name="new-person" v-model="newName">&nbsp;&nbsp;&nbsp;
      <label for="expl">explanation: </label>
      <input type="text" name="expl" v-model="explanation">&nbsp;&nbsp;

      <button @click="submit">Submit</button>
    </div>

</template>

<style>
.bording {
  background-color: rgb(166, 255, 0);
  border-radius: 3px;
  padding: 14px;
  margin-bottom: 28px;
}

.smallEl {
  display: block;
}

.hide-btn {
  float: right;
}

.navbar {
  margin-bottom: 15px;
}

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
}

</style>
