<template>
  <div class="container text-center">
    <div class="row">
      <GameSearch @game-search="gameSearch" />
    </div>
    <div class="row">
      <div class="col">
        <CreateVideogame @add-game="addGame" title="Nuevo Videojuego" />
      </div>
      <div class="col">
        <div v-if="game !== null" class="row">
          <GameDetails :gameSelected="game" @clear-game="clearGame" />
        </div>
        <ListVideogames
          :game-list="gameList"
          @game-detail="gameDetail"
          title="Videojuegos"
        />
      </div>
    </div>
  </div>
</template>

<script>
import GameSearch from "@/components/GameSearch.vue";
import CreateVideogame from "@/components/CreateVideogame.vue";
import ListVideogames from "@/components/ListVideogames.vue";
import GameDetails from "@/components/GameDetails.vue";
//import GameDetailsModal from "@/components/GameDetailsModal.vue";

export default {
  name: "HomeView",
  components: {
    GameSearch,
    CreateVideogame,
    ListVideogames,
    GameDetails,
    //GameDetailsModal,
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
    gameSearch() {},
    clearGame() {
      this.game = null;
    },
  },
};
</script>

<style scoped>
.home {
  height: auto;
  display: flex;
  background-color: rgb(197, 197, 197);
}
</style>
