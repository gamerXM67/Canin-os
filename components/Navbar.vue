<template>
    <nav>
        <img src="../src/assets/dogico.webp" alt="Logo de Caninos" class="logo">
        <a href="#Index">Accueil</a>
        <a href="#Presentation">Présentation</a>
        <a href="#Services">Services</a>
        <a href="#Tarifs">Tarifs</a>
        <a href="#Galerie">Galerie</a>
        <a href="#Avis">Avis</a>
        <a href="#Faq">faq</a>
        <a href="#Contact" class="btn-rdv">Prendre RDV</a>
        <div class="socials">
            <a class="social-item" href="https://www.facebook.com/" target="_blank">
                <img src="../src/assets/facebook.webp" alt="Facebook">
            </a>
            <a class="social-item" href="https://www.instagram.com/" target="_blank">
                <img src="../src/assets/instagram.webp" alt="Instagram">
            </a>
            <a class="social-item" href="https://www.twitter.com/" target="_blank">
                <img src="../src/assets/twitter.webp" alt="Twitter">
            </a>
            <a class="social-item" href="https://www.youtube.com/" target="_blank">
                <img src="../src/assets/youtube.webp" alt="Youtube">
            </a>
        </div>
    </nav>
</template>
<style scoped>
.logo {
    height: 48px;
    object-fit: contain;
}

nav {
    display: flex;
    background-color: #ac3939;
    justify-content: space-between;
    top: 0px;
    position: fixed;
    width: 100%;
    left: 0px;
}

.socials {
    display: flex;
    gap: 8px;

}

.socials img {
    height: 24px;
    object-fit: contain;
}
</style>