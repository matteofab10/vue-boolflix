<template>

    <div class="flip-card">
      <div class="flip-card-inner">
        <div class="flip-card-front">
            <img :src="image" :alt="title">
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
              <img class="language-flag" 
                src="../assets/img/it.png" alt="italian-flag"
                v-if="originalLanguage == 'it'"
              >
              <img class="language-flag" 
                src="../assets/img/en.png" alt="uk-flag"
                v-else-if="originalLanguage == 'en'"
              >
              <p v-else>{{originalLanguage}}</p>
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
      img.language-flag {
        width: 30px;
        vertical-align: middle;
      }
      p {
        display: inline-block;
      }
    }
  }
}

</style>