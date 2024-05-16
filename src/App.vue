<!-- <template>
  <label class="player-count"> Колличество игроков: 
    <input type="number" class="player-count__index" v-model="playerCount">
  </label>
  <div class="player-container">
    <player v-for="index in playerCount" :key="index" :playerCount="index" />  
  </div>
</template>

<script>
import Player from "./components/player.vue"

export default {
  components:{
    Player,
  },
  data() {
    return {
      playerCount: 1,
    }
  }
}

</script>

<style>
*{
  margin: 0;
  padding: 0;
}
</style>
<style lang="scss" scoped>
.player-container{
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
}
</style> -->


<!-- App.vue -->
<!-- <template>
  <div id="app">
    <label class="player-count">Количество игроков:
      <input type="number" class="player-count__index" v-model="playerCount" @input="updatePlayers">
    </label>
    <div class="player-container">
      <player v-for="(player, index) in players" :key="index" :playerCount="index + 1" :bgColor="player.bgColor" @endTurn="endTurn(index)" />
    </div>
  </div>
</template>

<script>
import Player from "./components/player.vue"

export default {
  components: {
    Player,
  },
  data() {
    return {
      playerCount: 1,
      players: [],
      currentPlayerIndex: 0,
    };
  },
  methods: {
    updatePlayers() {
      this.players = Array.from({ length: this.playerCount }, () => ({ bgColor: 'white' }));
    },
    endTurn(playerIndex) {
      this.players[this.currentPlayerIndex].bgColor = 'white';
      this.currentPlayerIndex = (playerIndex + 1) % this.players.length;
      this.players[this.currentPlayerIndex].bgColor = 'lightblue';
    },
  },
  created() {
    this.updatePlayers(); // При создании компонента обновляем массив игроков
  },
};
</script>


<style>
/* Стили для App.vue */
</style>
<style lang="scss" scoped>
.player-container {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
}
</style> -->


<template>
  <div id="app">
    <Navigation />
    <!-- <label class="player-count">Количество игроков:
      <input type="number" class="player-count__index" v-model="playerCount" @input="updatePlayers">
    </label> -->
    <div class="playerContainer">
        <Player
        v-for="(player, index) in players"
        :key="index"
        :playerCount="index + 1"
        :bgColor="player.bgColor"
        @endTurn="endTurn(index)"
      />
        </div>
    </div>
      
</template>

<script>
import Navigation from './components/navigation.vue';
import Player from "./components/player.vue"

export default {
  components: {
    Player,
    Navigation,
  },
  data() {
    return {
      playerCount: 1,
      players: [],
      currentPlayerIndex: 0,
    };
  },
  methods: {
    updatePlayers() {
      this.players = Array.from({ length: this.playerCount }, () => ({ bgColor: 'white' }));
    },
    // endTurn(playerIndex) {
      // this.players[this.currentPlayerIndex].bgColor = 'white';
      // this.currentPlayerIndex = (playerIndex + 1) % this.players.length;
      // this.players[this.currentPlayerIndex].bgColor = 'lightblue';
    // },
  },
  created() {
    this.updatePlayers(); // При создании компонента обновляем массив игроков
  },
};
</script>

<style>
*{
  margin: 0px;
  padding: 0px;
  font-family: sans-serif;
}

</style>
<style lang="scss" scoped>
#app{ 
  margin: 0 auto;
  //width: 1080px;
  height: 720px;
  background: black;
  display: flex;
  flex-direction: column;
}
.playerContainer {
  width: 100%;
  height: 100%;
}
</style>
