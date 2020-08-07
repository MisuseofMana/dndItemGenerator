<template>
    <div id="MasterBox">
        <div class="columnFlex">

        <section class="rowFlex">
            <label for="one">Magical</label>
            <input type="radio" id="one" value="Magical" v-model="magicOrMundane">
        </section>    

        <section class="rowFlex">
            <label for="two">Mundane</label>
            <input type="radio" id="two" value="Mundane" v-model="magicOrMundane">
        </section>
     
        </div>

        <div class="columnFlex">
            <input type="radio" id="Dingle" value="Wapons" v-model="itemType">
            <label for="Dingle">Wapons</label>

            <input type="radio" id="Berry" value="Armoors" v-model="itemType">
            <label for="Berry">Armoors</label>

            <input type="radio" id="Sweet" value="I-Tim's" v-model="itemType">
            <label for="Sweet">I-Tims</label>

            <input type="radio" id="Fairy" value="Trankets" v-model="itemType">
            <label for="Fairy">Trankets</label>
        </div>

        <div id="Generation"> 
            <button>Loot Me, Daddy</button>
        </div>

        <div class="readout">
            <section>
                <h2>{{ itemName }}</h2>
                <p>{{ itemDescription }}</p>
            </section>
        </div>
    </div>
</template>

<script>

    export default {
        name: 'ItemGenerator',
        data() {
            return {
                itemName: 'Secret Chocolate Bar',
                itemDescription: 'stinky little something, that looks like poo, smells like poo, and taste like poo. Is actually a giant bar of gold with an illusion spell on it.',
                itemValue: 300,
                magicOrMundane: '',
                itemType: '',
            }
        },
    }
</script>

<style scoped>
    .readout {
        border: black solid 2px;
        width:64%;
        margin:10px auto;
        text-align:center;
    }
    .readout section {
        display:flex;
        flex-direction:column;
        justify-content:center;
        align-items:center;
    }
    .columnFlex {
        display:flex;
        flex-direction:column;
    }
    .rowFlex {
        display:flex;
        flex-direction:row;
    }
    #RadioColumnOne {
        
    }
    #RadioColumnTwo {

    }
    #MasterBox {
        
    }
    #Generation {

    }
</style>