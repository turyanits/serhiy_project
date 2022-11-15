<template>
  <form class="flex">
    <div class="left" v-for="(games, index) in listLeft" :key="index">
      <GamesCard :imgSrc="games.imgSrc" :title="games.title" />
      <input
        type="radio"
        name="vote"
        value="1"
        v-show="!result"
      />
      <meter
        value="20"
        min="0"
        max=" 100 "
        v-show="result"
      ></meter>
    </div>
    <div class="right" v-for="(games, index) in listRight" :key="index">
      <GamesCard :imgSrc="games.imgSrc" :title="games.title" />
      <input
        type="radio"
        name="vote"
        value="1"
        v-show="!result"
      />
      <meter
        value="20"
        min="0"
        max="100"
        v-show="result"
      ></meter>
    </div>
    <button @click="result = true" v-show="!result">Відправити</button>
  </form>
</template>

<script>
import GamesCard from "@/components/GameCard";
export default {
  name: "GamesList",
  components: { GamesCard },
  props: ["listLeft", "listRight"],
  data() {
    return {
      result: false,
    };
  },
  methods: {
    
  },
};
</script>

<style lang="scss" scoped>
.btn {
  align-items: center;
}
.flex {
  display: flex;
}
.left {
  background-color: rgb(255, 90, 90);
  align-items: left;
}
.right {
  background-color: rgb(72, 157, 255);
  align-items: right;
}
</style>
