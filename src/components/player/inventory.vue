<template>
    <div class="inventory">
        <div class="items">
            <ul>
                <li v-for="(item, index) in inventory" :key="index">
                    <p class="item" v-for="key in Object.keys(item)" :key="key">
                        {{ item[key] }}
                    </p>
                    <button @click="useItem(index)" class="use">Использовать</button>
                    <button @click="useItem(index)" class="del"><img src="../../img/redCross.svg" alt="" ></button>
                    
                    <!-- <img src="../img/redCross.svg" alt="" class="del"> -->
                </li>
            </ul>
        </div>
        <!-- <div class="items">
            <ul>
                <li v-for="(item, index) in inventory" :key="index">
                    <p class="item"  v-for="i in item">
                        {{ i }}
                    </p>
                    <button @click="useItem(index)">Использовать</button>
                </li>
            </ul>
        </div> -->
        <button @click="createItem()" class="create">Создать</button>
    </div>
</template>


<script>
import item from "../item"
export default {
    name: "Inventory",
    data() {
        return {
            inventory: [],
        };
    },
    methods: {
        createItem() {
            // метод для создания предмета 
            this.inventory.push(item[Math.floor(Math.random() * item.length)])
            console.log(this.inventory)
        },
        useItem(index) {
             // Метод для удаления предмета из инвентаря при его использовании
            this.inventory.splice(index, 1)
        },
    },
}
</script>

<style scoped lang="scss">
.inventory {
    position: relative;
    height: 100%;
    .items{
        height: 90%;
        overflow-y: scroll;
        scrollbar-color:  red black;
        scrollbar-width:thin;
        ul{
            li{
                list-style: none;
                margin-bottom: 20px;
                position: relative;
                padding-bottom: 15px;
                border-bottom: 1px solid white;
                .del{
                    position: absolute;
                    top: 0px;
                    right: 0px;
                    background: none;
                    border: none;
                }
                .use{
                    position: absolute;
                    bottom:0px;
                    right: 0px;
                }
            }
        }
    }
    .create{
        position: absolute;
        bottom: 0px;
    }
}
</style>