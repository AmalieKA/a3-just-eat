<style scoped>
    #canvas {
        width: 390px;
        height: 844px;
    }

    #mainscreen {
        width: 390px;
        height: 844px;
        object-fit: cover;
    }

    #button {
        position: absolute;
        top:700px;
        background-color: #FB6603;
        border-radius: 100px;
        width: 370px;
        height: 45px;
        margin: 0px 10px;
        display: flex;
        gap: 10px;
    }

</style>

<template>
    <div id="canvas">
        <img id="mainscreen" src="./assets/mainscreen.PNG">
        <div id="button">
            <img src="" alt="">
        </div>
    </div>
</template>

<script setup>

</script>