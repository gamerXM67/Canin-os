<template>
    <section id="Presentation">
        <div class="container">
            <div class="grid">
                <figure class="image-wrapper">
                    <img id="ludosins" src="../src/assets/ludosins.webp" alt="Ludovic, toiletteur chez Pattes à l'eau">
                </figure>

                <article id="Apropos">
                    <header>
                        <span class="badge">Votre expert</span>
                        <h1>Rencontrez Ludovic, votre toiletteur dédié</h1>
                    </header>

                    <div class="text-content">
                        <p>
                            Je m'appelle Ludovic, artisan toiletteur spécialisé pour chiens et chats. Basé à
                            <span class="highlight">Niederschaeffolsheim</span>, j'ai transformé ma passion en métier
                            après une formation certifiante en 2022.
                        </p>

                        <p>
                            Passionné par l'équilibre émotionnel des animaux, j'ai complété mon savoir-faire en 2024
                            avec un diplôme de
                            <span class="highlight">Caresseur de chien professionelle</span>. Cette double compétence me
                            permet d'offrir un soin qui va au-delà de la simple esthétique.
                        </p>

                        <p>
                            Fort de mon expérience en protection animale, je vous accueille dans un environnement calme
                            et bienveillant, où chaque détail est pensé pour le confort et la sérénité de votre
                            compagnon.
                        </p>
                    </div>
                </article>
            </div>
        </div>
    </section>
</template>

<style scoped>
#Presentation {
    padding: 100px 20px;
    display: flex;
    justify-content: center;
}

.container {
    max-width: 1100px;
    width: 100%;
}

.grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 60px;
    align-items: center;
}

.image-wrapper {
    margin: 0;
    justify-self: center;
}

#ludosins {
    width: 100%;
    max-width: 420px;
    border-radius: 30px;
    box-shadow: 0 20px 40px rgba(0, 0, 0, 0.06);
    border: 8px solid rgba(255, 255, 255, 0.5);
    /* Transition douce pour l'effet de zoom au survol */
    transition: transform 0.4s ease;
}

#ludosins:hover {
    transform: scale(1.02);
}

#Apropos {
    background: rgba(255, 255, 255, 0.5);
    padding: 40px;
    border-radius: 24px;
    box-shadow: 0 10px 30px rgba(0, 0, 0, 0.03);
}

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
    font-size: 2.2rem;
    color: #2c3e50;
    margin-bottom: 24px;
}

.text-content p {
    font-size: 1.05rem;
    color: #5a5a5a;
    line-height: 1.7;
    margin-bottom: 18px;
}

.highlight {
    color: #dc8c82;
    font-weight: 700;
}

@media (max-width: 900px) {
    .grid {
        grid-template-columns: 1fr;
        text-align: center;
        gap: 40px;
    }
}
</style>