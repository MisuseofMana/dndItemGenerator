<template>
    <div id="MasterBox">
        <header>
            <h1>ITEM GENERATOR</h1>
        </header>
        
        <div class="columnFlex">
            <label for="Magical">Magical</label>
            <input type="checkbox" id="Magical" value="Magical">
        
            <label for="Mundane">Mundane</label>
            <input type="checkbox" id="Mundane" value="Mundane">
        </div>

        <div class="columnFlex">
            <input type="checkbox" id="Weapons" value="Wapons">
            <label for="Weapons">Wapons</label>

            <input type="checkbox" id="Armors" value="Armoors">
            <label for="Armors">Armoors</label>

            <input type="checkbox" id="Items" value="I-Tim's">
            <label for="Items">I-Tims</label>

            <input type="checkbox" id="Trinkets" value="Trankets">
            <label for="Trinkets">Trankets</label>
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