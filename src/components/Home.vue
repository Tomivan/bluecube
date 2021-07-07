<template>
  <div class="home">
    <div class="top">
      <div class="input">
        <i class="fa fa-search search-icon" aria-hidden="true"></i>
        <input type="text" placeholder="Find Something...">
        <button class="search"> Search </button>
      </div>
      <i class="fa fa-bell notification" aria-hidden="true"></i>
      <div class="profile">
        <i class="fa fa-user-circle user" aria-hidden="true"></i>
        <p>Abigail</p>
      </div>
    </div>
    <hr>
    <section class="category">
      <div class="box">
        <p>World</p><i class="fa fa-angle-down icon" aria-hidden="true"></i>
      </div>
      <div class="box">
        <p>Following</p><i class="fa fa-angle-down icon" aria-hidden="true"></i>
      </div>
      <div class="box">
        <p>Popular</p><i class="fa fa-angle-down icon" aria-hidden="true"></i>
      </div>
      <div class="box">
        <p>Post</p><i class="fa fa-angle-down icon" aria-hidden="true"></i>
      </div>
      <div class="box">
        <p>Gender</p><i class="fa fa-angle-down icon" aria-hidden="true"></i>
      </div>
      <div class="box">
        <p>Location</p><i class="fa fa-angle-down icon" aria-hidden="true"></i>
      </div>
      <div class="box">
        <p>Profession</p><i class="fa fa-angle-down icon" aria-hidden="true"></i>
      </div>
      <div class="box">
        <p>World</p><i class="fa fa-angle-down icon" aria-hidden="true"></i>
      </div>
    </section>
    <section class="image-card">
      <div class="card" v-for="(item, index) in photoUrls" :key="{index}">
        <img :src="item.small" alt="" class="photo">
      </div>
    </section>
  </div>
</template>

<script>
export default {
  name: 'Home',
  data() {
    return {
      photoUrls: [],
      names: []
    }
    },
    created() {
      this.getUnsplashPhotos()
  },

  methods: {
    getUnsplashPhotos() {
     const headers = { "Authorization": "Client-ID jF5H3GQKQhaKdSecL9UestPChaSxMAaUaUps5oXopbc"};
  fetch("https://api.unsplash.com/photos",  { headers })
    .then(response => response.json())
    .then(data => {
        console.log('data: ', data)
        const photos = data;
  if (photos) {
        this.photoUrls = photos.map(p => p.urls);
      }
  if (photos) {
    this.names = photos.map(p => p.user)
  }
    })
    .catch(error => console.log('error: ', error))
  }
  }
}


</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.home{
  margin-left: 3%;
}
.top{
  display: flex;
  width: 80vw;
  justify-content: space-between;
}
.input{
  display: flex;
}
.search-icon{
  position: absolute;
  margin: 1% 0 0 2%;
}
input{
  height: 7vh;
  width: 65vw;
  border: 1px solid #0000001e;
  border-radius: 5px;
}
input::placeholder{
  padding-left: 5em;
}
.search{
  background: navy;
  color: #fff;
  height: 5vh;
  width: 8vw;
  border: none;
  border-radius: 5px;
  margin: 1% 0 0 -12%;
}
.notification{
  height: 8vh;
  margin-left: -10%;
}
.category, .profile{
  display: flex;
}
.user{
  height: 4vh;
  padding: 0.8em;
}
.box{
  width: 8vw;
  height: 3vh;
  padding: 0.5em;
  border: 1px solid #0000001e;
  text-align: center;
  display: flex;
}
.box p{
  margin-top: 1%;
}
.image-card{
  display: flex;
  flex-wrap: wrap;
  margin-top: 2%;
}
.card{
  margin: 0 2% 2% 0;
}
.photo{
  width: 14vw;
  height: 30vh;
  border-radius: 5px;
}
.icon{
  margin: 3% 0 0 15%;
}
@media(min-width: 320px) and (max-width: 767px) {
  .home{
    margin-top: 20%;
  }
  .top{
    margin-left: -25%;
  }
  .search-icon{
    margin-top: 5%;
  }
  input{
    width: 50vw;
  }
  input::placeholder{
    padding-left: 2em;
    font-size: 12px;
  }
  .search{
    margin: 4% 0 0 -25%;
    width: 15vw;
  }
  .notification{
    margin-left: -15%;
  }
  hr{
    margin-left: -25%;
    width: 100%;
  }
  .category{
    margin-left: -25%;
    flex-wrap: wrap;
  }
  .box{
    width: 35vw;
  }
  .card{
    margin-left: -25%;
  }
  .photo{
    width: 80vw;
  }
}
@media(min-width: 768px) and (max-width: 1024px){
  .top{
    width: 72vw;
  }
  input{
    width: 55vw;
  }
  .search-icon{
    margin-top: 4%;
  }
  input::placeholder{
    padding-left: 3em;
  }
  .search{
    height: 4vh;
    margin: 4% 0 0 -15%;
  }
  .profile{
    margin-top: 1%;
  }
  .profile p{
    margin-top: 25%;
  }
  hr{
    width: 90%;
    margin-left: 0;
  }
  .category{
    flex-wrap: wrap;
  }
  .box{
    width: 15vw;
  }
}
</style>
