<template>

    <div class="flip-card">
      <div class="flip-card-inner">
        <div class="flip-card-front">
            <img :src="image" :alt="title">
        </div>
        <div class="flip-card-back">
          <p>{{title}}</p> 
          <p>{{originalTitle}}</p>
          <p>{{originalLanguage}}</p>
          <p>{{voteAverage}}</p>
        </div>
      </div>
    </div>
  
</template>

<script>
export default {
  name: 'Card',
  props: {
    title: String,
    image: String,
    originalTitle: String,
    originalLanguage: String,
    voteAverage: Number,
  },
}
</script>

<style lang="scss">
  @import "../assets/style/vars.scss";

  .flip-card {
  background-color: transparent;
  width: 200px;
  height: 300px;
  perspective: 1000px;
  display: inline-block;
  padding: 5px;
}
.flip-card-inner {
  position: relative;
  width: 100%;
  height: 100%;
  text-align: center;
  transition: transform 1.5s;
  transform-style: preserve-3d;
}
.flip-card:hover .flip-card-inner {
  transform: rotateY(180deg);
}
.flip-card-front, .flip-card-back {
  position: absolute;
  width: 100%;
  height: 100%;
  -webkit-backface-visibility: hidden;
  backface-visibility: hidden;
}
.flip-card-front {
  background-color: #bbb;
  color: black;
  border-radius: 10px;
  img {
    width: 100%;
    height: 100%;
    border-radius: 10px;
  }
}
.flip-card-back {
  background-color: black;
  color: white;
  transform: rotateY(180deg);
  border-radius: 10px;
  p {
    display: flex;
    justify-content: center;
    align-content: center;
    align-items: center;
    padding-top: 10px;
    margin-top: 20px;
  }
}

</style>