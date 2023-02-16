<template>
  <div class="calculator">
    <input type="text" v-model="display" disabled>
    <div class="buttons">
      <button v-for="button in buttons" :key="button.text" @click="handleClick(button)">{{ button.text }}</button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      display: "",
      buttons: [
        { text: "7" },
        { text: "8" },
        { text: "9" },
        { text: "+" },
        { text: "4" },
        { text: "5" },
        { text: "6" },
        { text: "-" },
        { text: "1" },
        { text: "2" },
        { text: "3" },
        { text: "*" },
        { text: "0" },
        { text: "." },
        { text: "/" },
        { text: "C" },
        { text: "=" }
      ]
    };
  },
  methods: {
    handleClick(button) {
      const { text } = button;
      if (text === "C") {
        this.display = "";
      } else if (text === "=") {
        this.display = eval(this.display);
      } else {
        this.display += text;
      }
    }
  }
};
</script>

<style>
.calculator {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

input {
  width: 100%;
  margin-bottom: 20px;
  padding: 10px;
  font-size: 20px;
  text-align: right;
}

.buttons {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-gap: 10px;
}

button {
  padding: 10px;
  font-size: 20px;
  background-color: #ccc;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  transition: background-color 0.2s ease-in-out;
}

button:hover {
  background-color: #aaa;
}

button:active {
  background-color: #888;
}
</style>