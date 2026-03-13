<script setup lang="ts">
import { ref } from 'vue'

// État pour gérer l'ouverture du menu mobile
const isMenuOpen = ref(false)

// Fonction pour basculer l'état du menu (ouvert/fermé)
const toggleMenu = () => {
    isMenuOpen.value = !isMenuOpen.value
}
</script>

<template>
    <nav class="navbar">
        <a href="#Index" class="logo-link" @click="isMenuOpen = false">
            <img src="../src/assets/dogico.webp" alt="Logo de Caninos" class="logo">
        </a>

        <button class="burger" @click="toggleMenu" :class="{ 'is-active': isMenuOpen }" aria-label="Menu">
            <span></span> <!-- Trois lignes du burger -->
            <span></span>
            <span></span>
        </button>

        <div class="nav-content" :class="{ 'is-open': isMenuOpen }">
            <ul class="nav-list">
                <li><a href="#Index" @click="isMenuOpen = false">Accueil</a></li>
                <li><a href="#Presentation" @click="isMenuOpen = false">Présentation</a></li>
                <li><a href="#Services" @click="isMenuOpen = false">Services</a></li>
                <li><a href="#Tarifs" @click="isMenuOpen = false">Tarifs</a></li>
                <li><a href="#Galerie" @click="isMenuOpen = false">Galerie</a></li>
                <li><a href="#Avis" @click="isMenuOpen = false">Avis</a></li>
                <li><a href="#Faq" @click="isMenuOpen = false">FAQ</a></li>
                <li><a href="#Contact" class="btn-rdv" @click="isMenuOpen = false">Prendre RDV</a></li>
            </ul>

            <ul class="socials">
                <li>
                    <a href="https://www.facebook.com" target="_blank" rel="noopener" class="social-item">
                        <img src="../src/assets/facebook.webp" alt="Facebook">
                    </a>
                </li>
                <li>
                    <a href="https://www.instagram.com" target="_blank" rel="noopener" class="social-item">
                        <img src="../src/assets/instagram.webp" alt="Instagram">
                    </a>
                </li>
                <li>
                    <a href="https://www.twitter.com" target="_blank" rel="noopener" class="social-item">
                        <img src="../src/assets/twitter.webp" alt="Twitter">
                    </a>
                </li>
                <li>
                    <a href="https://www.youtube.com" target="_blank" rel="noopener" class="social-item">
                        <!-- noopener evite le fishing -->
                        <img src="../src/assets/youtube.webp" alt="Youtube">
                    </a>
                </li>
            </ul>
        </div>
    </nav>
</template>

<style scoped>
/* Box-sizing : garantit que le padding ne dépasse pas la largeur de l'écran */
* {
    box-sizing: border-box;
}

.navbar {
    display: flex;
    background-color: rgb(255, 253, 246);
    justify-content: space-between;
    align-items: center;
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    max-width: 100vw;
    z-index: 1000;
    box-shadow: 0 6px 18px rgba(0, 0, 0, 0.08);
    padding: 12px 40px;
}

.logo {
    height: 48px;
    object-fit: contain;
}

.nav-content {
    display: flex;
    align-items: center;
    gap: 30px;
}

.nav-list,
.socials {
    display: flex;
    list-style: none;
    gap: 10px;
    margin: 0;
    padding: 0;
}

.nav-list a {
    padding: 10px 16px;
    border-radius: 12px;
    text-decoration: none;
    font-weight: 600;
    color: #1c1c1c;
    border: 1px solid rgba(220, 140, 130, 0.4);
    background: rgba(255, 255, 255, 0.9);
    transition: all 160ms ease;
}

.nav-list a:hover {
    transform: translateY(-3px);
    background: #fff;
}

.btn-rdv {
    background-color: #dc8c82 !important;
    color: white !important;
    border: none !important;
}

.socials {
    gap: 12px;
}

.socials img {
    height: 22px;
    transition: 0.2s;
}

.socials img:hover {
    transform: scale(1.15);
}

.burger {
    display: none;
}

/* --- CONFIGURATION MOBILE --- */
@media (max-width: 1150px) {
    .navbar {
        padding: 12px 20px;
    }

    /* Le burger remplace le menu horizontal */
    .burger {
        display: flex;
        flex-direction: column;
        gap: 6px;
        background: none;
        border: none;
        cursor: pointer;
        z-index: 1100;
    }

    .burger span {
        width: 28px;
        height: 3px;
        background: #dc8c82;
        border-radius: 5px;
        transition: 0.3s ease;
    }

    /* Animation du burger en croix (X) quand actif */
    .burger.is-active span:nth-child(1) {
        transform: translateY(9px) rotate(45deg);
    }

    .burger.is-active span:nth-child(2) {
        opacity: 0;
    }

    .burger.is-active span:nth-child(3) {
        transform: translateY(-9px) rotate(-45deg);
    }

    /* Transformation du menu en volet latéral coulissant */
    .nav-content {
        position: fixed;
        top: 0;
        right: -100%;
        /* Sorti de l'écran par la droite */
        width: 280px;
        height: 100vh;
        background: rgb(255, 253, 246);
        flex-direction: column;
        padding: 100px 20px;
        box-shadow: -10px 0 30px rgba(0, 0, 0, 0.1);
        transition: 0.4s cubic-bezier(0.4, 0, 0.2, 1);
        overflow-x: hidden;
        /* Empêche le scroll horizontal quand le menu est ouvert */
    }

    /* Fait glisser le menu vers l'intérieur de l'écran */
    .nav-content.is-open {
        right: 0;
    }

    .nav-list,
    .socials {
        flex-direction: column;
        width: 100%;
        gap: 15px;
    }

    .nav-list a {
        display: block;
        text-align: center;
        width: 100%;
    }

    .socials {
        flex-direction: row;
        justify-content: center;
        margin-top: 30px;
    }
}
</style>