<template>
    <header>

        <h1>Shib and Daveys Gerblin Treasuer</h1>
        
        <section>
            <button @click="$emit('change-page', 'item')">Item Generator</button>
            <button @click="$emit('change-page', 'char')">Character Generator</button>
        </section>
        <img src="@/assets/imgs/banner.png" alt="">
    </header>
</template>

<script>
    export default {
        name: 'SiteHeader',
        methods: {
            
        }
    }
</script>

<style scoped>
h1 {
    padding: 10px 0px 0px 10px;
    margin:0px;
    color: goldenrod;
}

section button {
    padding:10px;
    
}

section {
    width:600px;
    display:flex;
    justify-content:space-around;
    align-items:center;
}

header {
    background:darkslateblue;
    height:100px;
    display:flex;
    justify-content:space-between;
    align-items:center;
}

header img {
    height: 100px;
}
</style>