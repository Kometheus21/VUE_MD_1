<template>
    <div class="aboutMe">
      <h1>ABOUT ME</h1>
      <h3>Name: {{ user.name }}</h3>
      <h3>Surname: {{ user.surname }}</h3>
      <h3>ViA Code: {{ user.code }}</h3>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        user: {
          name: "Kristers",
          surname: "Skrebs",
          code: "IT21022",
        },
      };
    },
  };
  </script>
  
  <style scoped>
  .aboutMe {
    background-color: #fff; 
    color: #333; 
    padding: 20px;
    text-align: center;
    border-radius: 5px;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.5);
    width: 100%;
    max-width: 800px; 
    margin: 20px auto;
  }
  
  h1 {
    font-size: 28px;
    margin-bottom: 20px;
  }
  
  h3 {
    font-size: 18px;
    margin: 10px 0;
  }
  </style>