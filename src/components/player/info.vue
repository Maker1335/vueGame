<template>
    <div class="info">
        <!-- <p>номер игрока:{{ player[0] }}</p> -->
        <p>номер хода: {{ player[1] }}</p>
        <p>номер клетки: {{ player[2] }}</p>
        <!-- <p>позиция:{{ player[3] }}</p> -->
        <p>бонусные очки: {{ player[4] }}</p>
    </div>
</template>

<script>
export default {
    name: "Info",
    props: {
        player: Array,
    },
    methods: {
        a() {
            console.log(this.player)
        },
    },
}
</script>

<style scoped lang="scss">
.info {
    display: flex;
    justify-content: space-around;
}
</style>