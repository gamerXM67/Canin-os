<script setup>
import { ref } from 'vue';
import doge1 from '../src/assets/doge1.webp';
import doge2 from '../src/assets/doge2.webp';
import doge3 from '../src/assets/doge3.webp';

const images = ref([
    { url: doge1, alt: "Doge 1" },
    { url: doge2, alt: "Doge 2" },
    { url: doge3, alt: "Doge 3" }
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
        <div class="container">
            <header class="header">
                <span class="badge">Galerie</span>
                <h1>Les résultats en images</h1>
            </header>

            <section class="slider-container" aria-label="Galerie">
                <button class="slider-btn prev" @click="prev" aria-label="Précédent">‹</button>

                <transition name="fade" mode="out-in">
                    <img :key="currentIndex" :src="images[currentIndex].url" :alt="images[currentIndex].alt"
                        class="slider-image" />
                </transition>

                <button class="slider-btn next" @click="next" aria-label="Suivant">›</button>

                <div class="dots">
                    <span v-for="(_, index) in images" :key="index"
                        :class="['dot', { active: index === currentIndex }]"></span>
                </div>
            </section>
        </div>
    </section>
</template>

<style scoped>
/* --- Fond et Structure --- */
#Galerie {
    padding: 100px 20px;
    text-align: center;
}

.container {
    max-width: 1100px;
    margin: 0 auto;
}

.header {
    margin-bottom: 40px;
}

/* --- Badge Corail --- */
.badge {
    display: inline-block;
    background-color: #dc8c82;
    color: white;
    padding: 4px 16px;
    border-radius: 20px;
    font-size: 0.8rem;
    font-weight: 700;
    text-transform: uppercase;
    margin-bottom: 15px;
}

h1 {
    font-size: 2.4rem;
    color: #2c3e50;
    margin: 0;
}

/* --- Slider --- */
.slider-container {
    position: relative;
    display: inline-block;
    max-width: 100%;
    width: 650px;
    /* Légèrement plus large pour mettre en valeur les photos */
    margin-top: 20px;
}

.slider-image {
    display: block;
    width: 100%;
    height: 450px;
    /* Hauteur fixe pour éviter que la page "saute" */
    object-fit: cover;
    border-radius: 24px;
    /* Plus arrondi pour la douceur */
    /* ON NE TOUCHE PAS À L'OMBRE SELON TA DEMANDE */
    box-shadow: 0 12px 24px rgba(0, 0, 0, 0.18);
}

/* --- Boutons du Slider (Style Corail) --- */
.slider-btn {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    border: none;
    background: #dc8c82;
    /* Couleur corail pour le rappel */
    color: white;
    width: 50px;
    height: 50px;
    border-radius: 50%;
    cursor: pointer;
    font-size: 1.5rem;
    display: grid;
    place-items: center;
    transition: all 200ms ease;
    z-index: 10;
    box-shadow: 0 4px 12px rgba(220, 140, 130, 0.3);
}

.slider-btn:hover {
    background: #ca7b71;
    transform: translateY(-50%) scale(1.1);
}

.slider-btn.prev {
    left: -25px;
}

.slider-btn.next {
    right: -25px;
}

/* --- Indicateurs (Dots) --- */
.dots {
    margin-top: 20px;
    display: flex;
    justify-content: center;
    gap: 8px;
}

.dot {
    width: 8px;
    height: 8px;
    background: #ccc;
    border-radius: 50%;
    transition: all 0.3s ease;
}

.dot.active {
    background: #dc8c82;
    width: 20px;
    border-radius: 10px;
}

/* --- Animation Fade (Indispensable) --- */
.fade-enter-active,
.fade-leave-active {
    transition: opacity 0.4s ease;
}

.fade-enter-from,
.fade-leave-to {
    opacity: 0;
}

/* --- Responsive --- */
@media (max-width: 768px) {
    .slider-container {
        width: 90vw;
    }

    .slider-image {
        height: 300px;
    }

    .slider-btn {
        width: 40px;
        height: 40px;
    }

    .slider-btn.prev {
        left: 10px;
    }

    .slider-btn.next {
        right: 10px;
    }
}
</style>