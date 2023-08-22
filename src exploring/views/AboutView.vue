<template>
  <div class="about">
    <h1>Exploring Vue3 Concepts</h1>

    <!-- v-if & v-else -->
    <p v-if="showMessage">This message is shown.</p>
    <p v-else>This message is hidden.</p>

    <!-- v-show -->
    <p v-show="showMessage">This message can be toggled.</p>
    <button @click="toggleMessage">Toggle Message</button>
    
    <!-- v-for -->
    <ul>
    <li v-for="(item, index) in items" :key="index">{{ item }}</li>
    </ul>

    <!-- v-if & v-for -->
    <ul>
    <li v-for="(item, index) in items" :key="index">
      <span v-if="item.includes('1')">This item contains '1': {{ item }}</span>
      <span v-else>This item does not contain '1': {{ item }}</span>
    </li>
  </ul>

    <!-- v-model -->
    <div>
      <input type="text" class="form" v-model="textValue" />
      <p>Value: {{ textValue }}</p>
    </div>


  </div>
</template>

<script>
export default {
  data() {
    return {
      showMessage: true,
      items: ["Item 1", "Item 2", "Item 3"],
      textValue: '',
    };
  },

methods: {
   toggleMessage() {
     this.showMessage = !this.showMessage;
    },
  },
};
</script>


<style>
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}

ul {
  font-size: larger;
  margin-top: 10%;
}

p {
  font-size: larger;
  margin-top: 10%;
}

h1 {
  font-family: Arial, Helvetica, sans-serif;
  font-weight: 800;
}

.form {
  margin-top: 10%;
  width: 40%;
  min-height: 2vh;
  
}
</style>

