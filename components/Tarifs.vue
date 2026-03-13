<template>
    <section id="Tarifs">
        <div class="container">
            <header class="header">
                <span class="badge">Tarifs</span>
                <h1>Nos forfaits de toilettage</h1>
            </header>

            <div class="tableau">
                <article class="card">
                    <figure class="card-top">
                        <img src="../src/assets/dogeChat.webp" alt="Toilettage pour chats" />
                    </figure>
                    <footer class="card-bottom">
                        <h2>Chats</h2>
                        <p class="price-info">Tarifs sur demande</p>
                    </footer>
                </article>

                <article class="card">
                    <figure class="card-top">
                        <img src="../src/assets/dogeTresPetit.webp" alt="Chien de très petit gabarit" />
                    </figure>
                    <footer class="card-bottom">
                        <h2>Très petit gabarit</h2>
                        <p class="weight-info">&lt; 6 kg</p>
                    </footer>
                </article>

                <article class="card">
                    <figure class="card-top">
                        <img src="../src/assets/dogePetit.webp" alt="Chien de petit gabarit" />
                    </figure>
                    <footer class="card-bottom">
                        <h2>Petit gabarit</h2>
                        <p class="weight-info">&lt; 15 kg</p>
                    </footer>
                </article>

                <article class="card">
                    <figure class="card-top">
                        <img src="../src/assets/dogeMoyen.webp" alt="Chien de gabarit moyen" />
                    </figure>
                    <footer class="card-bottom">
                        <h2>Gabarit moyen</h2>
                        <p class="weight-info">&lt; 25 kg</p>
                    </footer>
                </article>

                <article class="card">
                    <figure class="card-top">
                        <img src="../src/assets/dogeGrand.webp" alt="Chien de grand gabarit" />
                    </figure>
                    <footer class="card-bottom">
                        <h2>Grand gabarit</h2>
                        <p class="weight-info">&lt; 40 kg</p>
                    </footer>
                </article>

                <article class="card">
                    <figure class="card-top">
                        <img src="../src/assets/dogeTresGrand.webp" alt="Chien de très grand gabarit" />
                    </figure>
                    <footer class="card-bottom">
                        <h2>Très grand gabarit</h2>
                        <p class="weight-info">&gt; 40 kg</p>
                    </footer>
                </article>
            </div>
        </div>
    </section>
</template>

<style scoped>
#Tarifs {
    padding: 100px 20px;
}

.container {
    max-width: 1100px;
    margin: 0 auto;
}

.header {
    text-align: center;
    margin-bottom: 60px;
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

.header h1 {
    font-size: 2.4rem;
    color: #2c3e50;
    margin-top: 10px;
}

.tableau {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 30px;
}

.card {
    background: rgba(255, 255, 255, 0.5);
    border-radius: 24px;
    box-shadow: 0 10px 30px rgba(0, 0, 0, 0.03);
    border: 1px solid rgba(255, 255, 255, 0.6);
    overflow: hidden;
    transition: all 0.3s ease;
    display: flex;
    flex-direction: column;
}

.card:hover {
    /* Effet d'élévation au survol */
    transform: translateY(-10px);
    box-shadow: 0 20px 40px rgba(0, 0, 0, 0.08);
    background: rgba(255, 255, 255, 0.8);
}

.card-top {
    width: 100%;
    aspect-ratio: 16 / 9;
    margin: 0;
}

.card-top img {
    width: 100%;
    height: 100%;
    object-fit: cover;
}

.card-bottom {
    padding: 25px 20px;
    text-align: center;
    flex-grow: 1;
    display: flex;
    flex-direction: column;
    justify-content: center;
}

.card h2 {
    margin: 0 0 10px;
    font-size: 1.2rem;
    color: #2c3e50;
    font-weight: 700;
}

.price-info,
.weight-info {
    margin: 0;
    font-size: 1rem;
    color: #dc8c82;
    font-weight: 600;
}

@media (max-width: 900px) {
    .tableau {
        grid-template-columns: repeat(2, 1fr);
    }
}

@media (max-width: 600px) {
    .tableau {
        grid-template-columns: 1fr;
    }

    h1 {
        font-size: 1.8rem;
    }
}
</style>