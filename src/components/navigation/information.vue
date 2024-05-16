<template>
    <div class="information">
        <p>Информация </p>
        <img src="../../img/инфо.svg" alt="">
    </div>
</template>
<script>
export default{
    name: 'Information',
}
</script>
<style scoped lang="scss">
.information{
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