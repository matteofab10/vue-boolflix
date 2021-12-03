<template>

    <div class="flip-card">
      <div class="flip-card-inner">
        <div class="flip-card-front">
            <img v-if="image" :src="image" :alt="title">
            <p v-else>PLACEHOLDER</p>
        </div>
        <div class="flip-card-back">
          <ul>
            <li>
              <strong>Titolo: </strong>
              <p v-if="title">
                {{title}}
              </p>
              <p v-else>{{name}}</p>
            </li>
            <li>
              <strong>Titolo originale: </strong>
              <p v-if="originalTitle">
                {{originalTitle}}
              </p>
              <p v-else>{{originalName}}</p>
            </li>
            <li>
              <strong>Lingua originale: </strong>
              <img class="flag" v-if="flags.includes(originalLanguage)" :src="require(`../assets/img/${originalLanguage}.png`)" :alt="title">
              <p v-else>{{originalLanguage}}</p>
            </li>
            <li>
              <strong>Voto: </strong>
                <i 
                v-for="(item, index) in 5"
                :key="index"
                class="fa-star"
                :class="index < Math.round(voteAverage/2) ? 'fas' : 'far'"></i>
            </li>
          </ul>
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
  data() {
    return {
      flags: ['it', 'en']
    }
  }
}
</script>

<style lang="scss" scoped>
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
  ul {
    padding: 10px 0;
    li {
      list-style: none;
      padding-bottom: 10px;
      margin-left: 5px;
      .flag {
        width: 30px;
        vertical-align: middle;
      }
      i {
        color: yellow;
        display: inline-block;
      }
      p {
        display: inline-block;
      }
    }
  }
}

</style>