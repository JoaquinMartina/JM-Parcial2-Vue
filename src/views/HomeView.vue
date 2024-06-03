<template>
  <div class="container text-center">
    <div class="row">
      <div class="col">
        <CreateVideogame @add-game="addGame" title="Nuevo Videojuego" />
      </div>
      <div class="col">
        <ListVideogames
          :game-list="gameList"
          @game-detail="gameDetail"
          title="Videojuegos"
        />
      </div>
    </div>
    <div v-if="game !== null">
      <GameDetails :game-selected="game" @clear-game="clearGame" />
    </div>
  </div>
</template>

<script>
import CreateVideogame from "@/components/CreateVideogame.vue";
import ListVideogames from "@/components/ListVideogames.vue";
import GameDetails from "@/components/GameDetails.vue";

export default {
  name: "HomeView",
  components: {
    CreateVideogame,
    ListVideogames,
    GameDetails,
  },
  data() {
    return {
      gameList: [],
      game: null,
    };
  },
  methods: {
    addGame(game) {
      this.gameList.push(game);
    },
    gameDetail(gameDetail) {
      this.game = gameDetail;
    },
    clearGame() {
      this.game = null;
    },
  },
};
</script>
