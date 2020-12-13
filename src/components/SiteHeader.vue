<template>
    <!-- header layout -->
    <header>
        <h1>Shib and Daveys Gerblin Treasuer</h1>
        
        <section class="buttonContainer">
            <!-- declares two buttons -->
            <!-- v-on:click = when clicked, emit change page event and payload to parent (app.vue) -->
            <button @click="$emit('change-page', 'item')">Item Generator</button>
            <!-- <button @click="$emit('change-page', 'char')">Character Generator</button> -->
        </section>

        <img src="@/assets/imgs/banner.png" alt="">

    </header>
</template>

<script>
    export default {
        name: 'SiteHeader',
    }
</script>

<style scoped>
/* scoped is VueJS for "private" */
header {
    background:darkslateblue;
    height:100px;
    width:100vw;
    display:flex;
    justify-content:space-between;
    align-items:center;
}

header img {
    height: 100px;
}

h1 {
    /* padding = top right bottom left: shorthand for writing each out */
    padding: 10px 0px 0px 10px;
    margin:0px;
    color: goldenrod;
}

 .buttonContainer button {
    /* padding ten pixels all around (shorthand) */
    padding:10px;
    
}

.buttonContainer {
    width:600px;
    display:flex;
    justify-content:space-around;
    align-items:center;
}


</style>