<template>
    <button
      @click="selectSection"
      :class="{ active: isActive }"
    >
      {{ buttonText }}
    </button>
  </template>
  
  <script>
  export default {
    props: {
      text: String,
      isActive: Boolean 
    },
    methods: {
      selectSection() {
        this.$emit('sectionSelected', this.text);
      }
    },
    computed: {
      buttonText() {
        return this.text.toUpperCase();
      }
    }
  }
  </script>
  
  <style scoped>
  button {
    background-color: #333;
    color: #fff;
    padding: 10px 20px;
    border: none;
    cursor: pointer;
  }
  
  button.active {
    background-color: #3498db;
    color: #fff;
  }
  </style>