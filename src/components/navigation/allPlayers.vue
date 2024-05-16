<template>
    <div class="allPlayers">
        <p>Все игроки </p>
        <img src="../../img/все игроки.svg" alt="">
    </div>
</template>
<script>
export default{
    name: 'AllPlayers',
}
</script>
<style scoped lang="scss">
.allPlayers{
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 20px;
    img{
        width: 30px;
        height: 30px;
    }
}
</style>