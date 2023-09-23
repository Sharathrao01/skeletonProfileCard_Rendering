<template>
    <div class="profile-card">
      <div class="profile-image">
        <img :src="userData.pic" />
      </div>
      <div class="profile-info">
        <span> Written By </span>
        <h3>{{ userData.name }}</h3>
        <p>{{ userData.bio }}</p>
      </div>
    </div>
  </template>
  
  <script>
  import { ref } from 'vue'
  const loadUserData = async () => {
    return new Promise((resolve) => {
      setTimeout(() => {
        resolve({
          name: 'Sharath',
          pic:
            'https://media.licdn.com/dms/image/D5603AQELyqS_bu81Vg/profile-displayphoto-shrink_800_800/0/1675007480601?e=2147483647&v=beta&t=3Vs_Wundn5zVegN2TPOwOQX7EIYl275ve9sFqOX9t6Y',
          bio:
            'Iam a front end developer, Iam very much interested in software development and keen on learning the new technologies',
        })
      }, 3000)
    })
  }
  
  export default {
    async setup() {
      const userData = ref(await loadUserData())
  
      return {
        userData,
      }
    },
  }
  </script>
  
  <style>
  .profile-card {
    width: 100%;
    max-width: 700px;
    min-height: 180px;
    background: rgb(131, 123, 101);
    margin: 0 auto;
    padding: 30px;
    box-sizing: border-box;
    overflow: hidden;
    border-radius: 20px;
    margin-top: 10px
  }
  
  .profile-image {
    width: 20%;
    float: left;
  }
  
  .profile-image img {
    width: 100%;
    height: auto;
    border-radius: 50%;
    border: 5px solid #42b883;
    padding: 5px;
  }
  
  .profile-info {
    width: 75%;
    float: right;
  }
  
  .profile-info span {
    text-transform: uppercase;
    color: #dd1010;
    letter-spacing: 3px;
  }
  
  .profile-info h3 {
    margin: 10px 0;
    font-size: 1.5em;
    color: #222;
  }
  
  .profile-info p {
    line-height: 140%;
    color: #830404;
  }
  </style>