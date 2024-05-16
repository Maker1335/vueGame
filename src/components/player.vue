<template>
    <div class="player" :class="'player' + playerCount">
        <div class="leftSide">
            <input type="text" v-model="player[5]" class="name">
            <playerMap />
            <info :player="player" />
        </div>
        <div class="rightSide">
            <inventory />
            <div class="buttons">
                <button class="rollTheDice">Бросить кубик</button>
                <button @click="$emit('endTurn', playerCount)" class="endTurn">Закончить ход</button>
            </div>
        </div>
    </div>
</template>

<script>
import Info from "./player/info.vue";
import Inventory from "./player/inventory.vue";
import PlayerMap from "./player/map.vue";

export default {
    name: "Player",
    components: {
        PlayerMap,
        Info,
        Inventory,
    },
    props: {
        playerCount: Number,
        bgColor: String,
        disabled: Boolean,
    },
    data() {
        return {
            name: "",
            count: 0,
            turn: 0,
            cellNumber: 0,
            position: 0,
            extraPoints: 0,
            player: [],
        };
    },
    methods: {},
    created() {
        this.count = this.playerCount;
        this.player.push(
            this.count,
            this.turn,
            this.cellNumber,
            this.position,
            this.extraPoints,
            this.name,
        );
    },
    watch: {
        "player.5": (newName) => {
            console.log(newName);
        },
    },
};
</script>

<style lang="scss">
.player {
    width: 100%;
    //width: 1024px;
    margin: 0 auto;
    height: 100%;
    background: rgb(0, 0, 0);
    color: white;
    display: flex;
    justify-content: space-between;

    .leftSide,
    .rightSide {
        width: 100%;
    }

    .leftSide {
        display: flex;
        flex-direction: column;
        justify-content: space-evenly;
        border-right:1px solid white;
        .name{
            display: flex;
            justify-content: space-around;
            align-items: center;
            width: 500px;
            margin: 0 auto;
            font-size: 20px;
        }
    }

    .rightSide {
        position: relative;
        border-left:1px solid white ;
        .buttons {
            button {
                position: absolute;
            }

            .rollTheDice {
                right: 110px;
                bottom: 0px;
            }

            .endTurn {
                right: 0px;
                bottom: 0px;
            }
        }
    }
}
</style>
<!-- <template>
    <div class="player" :class="'player' + playerCount">
        <playerMap />
        <info :player="player"/>
        <inventory />
    </div>
</template>

<script>
import Info from "./player/info.vue";
import Inventory from "./player/inventory.vue";
import PlayerMap from "./player/map.vue";

export default {
    name: "Player",
    components: {
        PlayerMap,
        Info,
        Inventory,
    },
    props: {
        playerCount: Number,
    },
    data() {
        return {
            count: 0, 
            turn: 0, 
            cellNumber: 0, 
            position: 0, 
            extraPoints: 0,
            player: []
        }
    },
    methods: {
    },
    created(){
        this.count = this.playerCount;
        this.player.push(this.count, this.turn, this.cellNumber, this.position, this.extraPoints);
        console.log(this.player);
    }
}
</script>

<style lang="scss">
.player {
    width: 33%;
    height: 700px;
    display: flex;
    flex-direction: column;
    gap: 20px;

    background: blueviolet;
}
</style> -->
<!-- Player.vue -->