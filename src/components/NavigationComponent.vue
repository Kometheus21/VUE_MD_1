<template>
    <nav class="navigation">
      <button
        v-if="loggedIn"
        v-for="section in sections"
        :key="section.text"
        @click="changeSection(section.text)"
        :class="{ active: section.text === currentSection }"
      >
        {{ section.text }}
      </button>
    </nav>
  </template>
  
  <script>
  export default {
    props: {
      loggedIn: Boolean,
    },
    data() {
      return {
        currentSection: "HOME",
        sections: [
          { text: "HOME" },
          { text: "ABOUT ME" },
        ],
      };
    },
    methods: {
      changeSection(section) {
        this.currentSection = section;
        this.$emit("sectionChange", section);
      },
    },
  };
  </script>
  
  <style scoped>
  .navigation {
    background-color: #333;
    color: #fff;
    padding: 10px;
    text-align: center;
    width: 100%;
    display: flex;
    justify-content: center;
  }
  
  button {
    background-color: #333;
    color: #fff;
    padding: 10px 20px;
    border: none;
    cursor: pointer;
    font-size: 16px;
    margin: 0 10px;
  }
  
  button.active {
    background-color: #3498db;
    color: #fff;
  }
  </style>