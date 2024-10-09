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

#buttonOrange {
    position: absolute;
    display: flex;
    top: 700px;
    background-color: #FB6603;
    border-radius: 100px;
    width: 300px;
    height: 25px;
    margin: 0px 10px;
    gap: 10px;
    padding: 10px 35px;
    justify-content: center;
    align-items: center;
}

#contents {
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 15px;
}

#bar {
    width: 220px;
    height: 6px;
    background-color: white;
    border-radius: 100px;
}

#elements {
    width: 220px;
    position: absolute;
    display: flex;
    align-items: center;
    transition: justify-content 5s ease;
}

#circle {
    position: absolute;
    display: flex;
    padding: 5px;
    border-radius: 100%;
    background-color: black;
}

#buttonGreen {
    position: absolute;
    display: flex;
    top: 700px;
    background-color: #0EA84F;
    border-radius: 100%;
    margin-right: 10px;
    justify-content: center;
    align-items: center;
    width: 25px;
    height: 25px;
}

#checkmark {
    width: 25px;
    height: 25px;
}
</style>

<template>
    <div id="canvas">
        <img id="mainscreen" src="./assets/mainscreen.PNG">
        <div id="buttonOrange" v-show="showOrange == true">
            <div id="contents">
                <img src="./assets/restaurant.svg">
                <div id="bar"></div>
                <img src="./assets/house.svg">
            </div>
            <div id="elements" :style="{ left: bikePosition + 'px' }">
                <div id="circle">
                    <img id="bike" src="./assets/Clip path group.svg" @click="moveToMiddle">
                </div>
            </div>
        </div>
        <div id="buttonGreen" v-show="showOrange == false">
            <img id="checkmark" src="">
        </div>
    </div>
    <button @click="moveToMiddle">Move order</button>
    <button @click="completeOrder">Complete order</button>
</template>

<script setup>
import { ref } from 'vue';

const bikePosition = ref(75);
const step = ref(3);
const maxValue = ref(275);

function moveToMiddle() {

    function animateCircle() { //creating the function

        if (bikePosition.value < maxValue.value) {
            bikePosition.value += step.value;
            requestAnimationFrame(animateCircle);
        } else {
            bikePosition.value = maxValue.value;
        }

    }

    animateCircle(); //using/executing the function
}

function openTracking() {

}

const showOrange = ref(true);

function completeOrder() {
    showOrange.value = false;
}


</script>