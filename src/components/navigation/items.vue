<template>
    <div class="items">
        <p>предметы</p>
        <img src="../../img/предметы.svg" alt="">
    </div>
</template>
<script>
export default{
    name: 'Items',
}
</script>
<style scoped lang="scss">
.items{
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