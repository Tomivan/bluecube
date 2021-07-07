<template>
<div class="sidebar">
  <div class="head">
    <img src="../assets/bluecube.png" class="logo">
    <p class="title">bluecube</p>
  </div>
  <section>
    <div class="route">
      <i class="fa fa-home icon" aria-hidden="true"></i>
      <p>Home</p>
    </div>
    <div  class="route">
      <i class="fa fa-inbox icon" aria-hidden="true"></i>
      <p>Message</p>
    </div>
  </section>
  <section class="section">
    <p> SHARE </p>
    <div  class="route">
      <i class="fa fa-bars icon" aria-hidden="true"></i>
      <p>Ranking</p>
    </div>
    <div  class="route">
      <i class="fa fa-anchor icon" aria-hidden="true"></i>
      <p>Challenge</p>
    </div>
    <div  class="route">
      <i class="fa fa-gift icon" aria-hidden="true"></i>
      <p>Party</p>
    </div>
    <div  class="route">
      <i class="fa fa-link icon" aria-hidden="true"></i>
      <p>Connect</p>
    </div>
    <div  class="route">
      <i class="fa fa-child icon" aria-hidden="true"></i>
      <p>Parade</p>
    </div>
    <div  class="route">
      <i class="fa fa-users icon" aria-hidden="true"></i>
      <p>Group</p>
    </div>
  </section>
</div>
</template>

<script>
export default {
  name: 'Sidebar'
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.sidebar{
  width: 12vw;
  height: 92.5vh;
  padding: 1em;
  border-right: 1px solid #0000001e;
}
.logo{
    height: 4vh;
    width: 2vw;
    margin-left: 8%;
}
.head{
  display: flex;
}
.title{
  color: lightblue;
  margin: 2% 0 0 3%;
}
.route{
  display: flex;
}
.icon{
  padding: 1em;
}
@media(min-width: 320px) and (max-width: 767px) {
  .sidebar{
    display: flex;
    border-right: none;
  }
  .logo{
    width: 8vw;
    height: 4vh;
  }
  .icon{
    padding: .6em;
  }
  .head p, .section p, .route p{
    display: none;
  }
  section{
    display: flex;
  }
}
@media(min-width: 768px) and (max-width: 1024px){
  .sidebar{
    width: 14vw;
  }
  .title{
    padding: .5em;
  }
  .logo{
    height: 3vh;
    width: 4vw;
  }
  .route{
    margin-left: -15%;
  }
}
</style>