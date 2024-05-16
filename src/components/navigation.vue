<template>
    <div class="navigation">
        <Information/>
        <Items/>
        <AllPlayers/>
    </div>
</template>
<script>
import AllPlayers from './navigation/allPlayers.vue';  
import Information from './navigation/information.vue';
import Items from './navigation/items.vue';
export default{
    name: "Navigation",
    components:{
        AllPlayers,
        Information,
        Items
    },
    
}
</script>
<style scoped lang="scss">
.navigation{
    display: flex;
    justify-content: space-around;
    border-bottom: 2px solid white;
    color:white;
    padding: 10px 0;
}
</style>