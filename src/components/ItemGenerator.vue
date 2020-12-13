<template>
    <div class="readout">

         <header>
            <h1>ITEM GENERATOR</h1>
        </header>
        
        <div class="columnFlex">
            <label for="Magical">Magical</label>
            <input type="checkbox" id="magic" value="magic" v-model="selectedBoxes">
        
            <label for="Mundane">Mundane</label>
            <input type="checkbox" id="Mundane" value="mundane" v-model="selectedBoxes">
        </div>

        <div class="columnFlex">
            <label for="Weapons">Wapons</label>
            <input type="checkbox" id="Weapons" value="weapon" v-model="selectedBoxes">

            <label for="Armors">Armoors</label>
            <input type="checkbox" id="Armors" value="armor" v-model="selectedBoxes">

            <label for="Items">I-Tims</label>
            <input type="checkbox" id="Items" value="item" v-model="selectedBoxes">

            <label for="Trinkets">Trankets</label>
            <input type="checkbox" id="Trinkets" value="trinket" v-model="selectedBoxes">
        </div>

        <div>
            <label for="NumberOfItems"># of Items to Generate</label>
            <input type="range" min="1" max="5" value="1" v-model="amountToGenerate">
        </div>

        <div>
            <ul>
                <li v-for="selected in selectedBoxes" :key="selected">{{ selected }}</li>
            </ul>
        </div>

        <section class="buttonContainer">
            <button @click="getItem">GET NEW ITEM</button>
        </section>

        <!-- : = v-bind -->
        <!-- v-for: iterates through each item in magicItems array -->
        <!-- renders div 'item' for each element/object in magicItem array -->
        <div class="item" v-for="item in currentItem" :key="item.id">
            
            <header class="row box nullBottomBorder">
                <!-- '{{ anything in these is template syntax }} -->
                <h1>{{ item.itemName }}</h1>
            </header>
            
            <!-- having space in classes applies both classes -->
            <section class="gridRow-3fr row" >
                <section class="box nullRightBorder nullBottomBorder">
                    <h2>Magical/Mundane:</h2>
                    <h1>{{  item.magicOrMundane  }}</h1>
                </section>

                <section class="box nullRightBorder nullBottomBorder">
                    <h2>Value:</h2> 
                    <h1>{{ item.itemValue }}</h1>
                </section>

                <section class="box nullBottomBorder">
                    <h2>Type:</h2>
                    <h1>{{  item.itemType  }}</h1>
                </section>
            </section>

            <section class="gridRow-1fr-2fr row"> 
                <section class="box nullRightBorder">
                    <h2>Enchantment(s):</h2>
                    <h1>{{  item.enchantment  }}</h1>
                </section>

                <section class="box">
                    <h2>Description:</h2>
                    <h1>{{ item.itemDescription }} </h1>
                </section>
            </section>
       </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            name:'ReadoutBlock',
            oldItemNumber: 0,
            selectedBoxes:[],
            amountToGenerate:1,
            // hard coded magicItem array filled with item objects to be displayed
            magicItems: [
            {
                id: 0,
                itemName: 'A Dead Fish',
                itemDescription: 'fish, orange, small, smell bad',
                itemValue: -2,
                magicOrMundane: 'mundane',
                itemType:'item',
                enchantment:'Phish',
            },
            {
                id: 1,
                itemName: 'Gerblin Cotton Onesie',
                itemDescription: 'warm, comforting, has a butt flap.',
                itemValue: 200,
                magicOrMundane: 'magic',
                itemType:'armor',
                enchantment:'when worn, goblins CAN NOT tell you how to live your life',
            },
            {
                id: 2,
                itemName: 'Toad Bungus and His Stick',
                itemDescription: 'uhh.. I dunno?',
                itemValue: 9999,
                magicOrMundane: 'magic',
                itemType:'trinket',
                enchantment:'maybe? >;)',
            },
            {
                id: 3,
                itemName: 'Questionable Chocolate',
                itemDescription: "somethings not right...",
                itemValue: 2,
                magicOrMundane: 'mundane',
                itemType:'weapon',
                enchantment:'+1 stank dmg',
            },
            {
                id: 4,
                itemName: 'Dandy Candyman Jones',
                itemDescription: "he's a pet rock that follows you everywhere.",
                itemValue: 300,
                magicOrMundane: 'magic',
                itemType: 'trinket',
                enchantment: '+2d6 on failed roll'
            },
            {
                id: 5,
                itemName: 'Broken Stick',
                itemDescription: "It was once a glorious branch, now it's a broken stick.",
                itemValue: 1,
                magicOrMundane: 'mundane',
                itemType: 'item',
                enchantment: 'none'
            },
            {
                id: 6,
                itemName: 'sticky goo',
                itemDescription: "Questionable material from a bug bear nest. Why would you keep this?",
                itemValue: 1,
                magicOrMundane: 'mundane',
                itemType: 'item',
                enchantment: 'useful for botions.'
            },
            {
                id: 7,
                itemName: 'Rowdy Boy Suit',
                itemDescription: "Makes you rough and tumble.",
                itemValue: 300,
                magicOrMundane: 'magic',
                itemType: 'armor',
                enchantment: '+1 Str, +1 Con, -2 Cha, good punching'
            },
            {
                id: 8,
                itemName: 'Borat Bannana Hammock',
                itemDescription: "Very nice! Can be used as a sling weapon.",
                itemValue: 2000,
                magicOrMundane: 'magic',
                itemType: 'armor',
                enchantment: '-1 Crotch AC'
            },
            {
                id: 9,
                itemName: 'A rattlesnake',
                itemDescription: "Literally a rattlesnake. Pick it up by the tail and slap people with it.",
                itemValue: 42069,
                magicOrMundane: 'magic',
                itemType: 'weapon',
                enchantment: '+2 Poison Dmg per hit. Hurts you for 1 damage per use.'
            },
            {
                id: 10,
                itemName: 'A Very Long Gun',
                itemDescription: "What is this mechanical item? It always crits, requires magic steel pebbles to use.",
                itemValue: 1200,
                magicOrMundane: 'magic',
                itemType: 'weapon',
                enchantment: '1d20 ATK + 20'
            },
        ],
        currentItem: [],
        }
    },
    methods: {
        getItem(){
            for(let i=1; i <= this.amountToGenerate.length; i++){
                const randomNumber = Math.floor(Math.random() * (this.magicItems.length) + 0);

                if (this.oldItemNumber == randomNumber){
                    this.getItem();
                }
                else {
                    let filteredArray;
                    this.oldItemNumber = randomNumber;

                        if(this.selectedBoxes.length === 0){
                            return
                        }
                        else {
                            
                            filteredArray = this.magicItems.filter(item => )
                        }

                }
            }
        }
    },
}
</script>

<style scoped>

.buttonContainer {
    margin:0 0 25px 0;
}

h1, h2 {
    padding:0;
    margin:0;
}

h1  {
    font-size:35px;
}

h2 {
    font-size:20px;
    padding: 10px;
    color:lightgrey;
}

.item {
    margin-bottom:25px;
}

.box {
    border:solid black 2px;
    padding:10px;
    display: flex;
}

.nullBottomBorder {
    border-bottom:none;
}

.nullRightBorder {
    border-right:none;
}

 .readout {
        width:64%;
        margin:10px auto;
    }
    .columnFlex {
        display:flex;
        background:green;
        margin:10px;
        flex-direction:row;
    }
    .gridRow-3fr {
        display:grid;
        grid-template-columns: repeat(3, 1fr);
    }

    .gridRow-1fr-2fr {
        display:grid;
        grid-template-columns: 1fr 2fr;
    }

header {
    text-align:left;
}
</style>