<script setup>
import { ref } from 'vue';
import doge1 from '../src/assets/doge1.webp';
import doge2 from '../src/assets/doge2.webp';
import doge3 from '../src/assets/doge3.webp';

const images = ref([
    doge1,
    doge2,
    doge3
]);
const currentIndex = ref(0);

const next = () => {
    currentIndex.value = (currentIndex.value + 1) % images.value.length;
};
const prev = () => {
    currentIndex.value = (currentIndex.value - 1 + images.value.length) % images.value.length;
};
</script>

<template>
    <section id="Galerie">
        <p>galerie</p>
        <h1>Les resultats</h1>
        <!-- <p class="slider-placeholder">GROSSE IMAGE DEFILANTE ICI</p> -->
        <section class="slider-container" aria-label="Galerie">
            <button class="slider-btn prev" @click="prev" aria-label="Précédent">‹</button>

            <transition name="fade" mode="out-in">
                <img :key="currentIndex" :src="images[currentIndex]" class="slider-image" />
            </transition>

            <button class="slider-btn next" @click="next" aria-label="Suivant">›</button>
        </section>
    </section>
</template>
<style scoped>
#Galerie {
    background-color: #FFD600;
    padding: 40px 0;
    text-align: center;
}

.slider-container {
    position: relative;
    display: inline-block;
    max-width: 90vw;
    width: 560px;
}

.slider-image {
    display: block;
    width: 100%;
    height: auto;
    border-radius: 14px;
    box-shadow: 0 12px 24px rgba(0, 0, 0, 0.18);
}

.slider-btn {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    border: none;
    background: rgba(0, 0, 0, 0.35);
    color: white;
    width: 44px;
    height: 44px;
    border-radius: 50%;
    cursor: pointer;
    font-size: 1.2rem;
    display: grid;
    place-items: center;
    transition: background 150ms ease;
}

.slider-btn:hover {
    background: rgba(0, 0, 0, 0.55);
}

.slider-btn.prev {
    left: -22px;
}

.slider-btn.next {
    right: -22px;
}

@media (max-width: 600px) {
    .slider-container {
        width: 90vw;
    }

    .slider-btn.prev {
        left: 6px;
    }

    .slider-btn.next {
        right: 6px;
    }
}
</style>