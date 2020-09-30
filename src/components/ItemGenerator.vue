<template>
    <div id="MasterBox">
        <header>
            <h1>ITEM GENERATOR</h1>
        </header>
        
        <div class="columnFlex">
            <label for="Magical">Magical</label>
            <input type="radio" id="Magical" value="Magical" v-model="magicOrMundane">
        
            <label for="Mundane">Mundane</label>
            <input type="radio" id="Mundane" value="Mundane" v-model="magicOrMundane">
        </div>

        <div class="columnFlex">
            <input type="radio" id="Weapons" value="Wapons" v-model="itemType">
            <label for="Weapons">Wapons</label>

            <input type="radio" id="Armors" value="Armoors" v-model="itemType">
            <label for="Armors">Armoors</label>

            <input type="radio" id="Items" value="I-Tim's" v-model="itemType">
            <label for="Items">I-Tims</label>

            <input type="radio" id="Trinkets" value="Trankets" v-model="itemType">
            <label for="Trinkets">Trankets</label>
        </div>

        <div id="Generation"> 
            <button>Loot Me, Daddy</button>
        </div>
        
    </div>
</template>

<script>


    export default {
        name: 'ItemGenerator',
        methods: {

        },
    }
</script>

<style scoped>

</style>