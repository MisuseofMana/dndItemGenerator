<template>
    <div class="readout">
        <div class="item" v-for="item in magicItems" :key="item.id">
        <header class="row box nullBottomBorder">
            <h1>{{ item.itemName }}</h1>
        </header>
        
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
            magicItems: [
            {
                id: 0,
                itemName: 'A Dead Fish',
                itemDescription: 'fish, orange, small, smell bad',
                itemValue: "-2 sp",
                magicOrMundane: 'mundane',
                itemType:'Fish',
                enchantment:'Phish',
            },
            {
                id: 1,
                itemName: 'Gerblin Cotton Onesie',
                itemDescription: 'warm, comforting, has a butt flap.',
                itemValue: '200gp',
                magicOrMundane: 'magic',
                itemType:'armor',
                enchantment:'when worn, goblins CAN NOT tell you how to live your life',
            },
            {
                id: 2,
                itemName: 'Toad Bungus and His Stick',
                itemDescription: 'uhh.. I dunno?',
                itemValue: 'unknown',
                magicOrMundane: 'cosmic',
                itemType:'infinite',
                enchantment:'maybe? >;)',
            },
            {
                id: 3,
                itemName: 'Questionable Chocolate',
                itemDescription: "somethings not right...",
                itemValue: ':)',
                magicOrMundane: 'poo',
                itemType:'throwable',
                enchantment:'+1 stank dmg',
            },
            {
                id: 4,
                itemName: 'Dandy Candyman Jones',
                itemDescription: "he's a pet rock that follows you everywhere.",
                itemValue: 300,
                magicOrMundane: 'of course',
                itemType: 'Friend',
                enchantment: '+2d6 on failed roll'
            }
        ]
        }
    },
}
</script>

<style scoped>

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