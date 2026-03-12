<template>
    <section id="Tarifs">
        <section class="header">
            <p>Tarifs</p>
            <h1>Nos forfaits de toilettage</h1>
        </section>

        <section class="tableau">
            <article class="card">
                <header class="card-top">
                    <img src="../src/assets/doge.webp" alt="Toilettage chats" />
                </header>
                <footer class="card-bottom">
                    <h2>Chats</h2>
                    <p>Tarifs sur demande</p>
                </footer>
            </article>

            <article class="card">
                <header class="card-top">
                    <img src="../src/assets/doge.webp" alt="Très petit gabarit" />
                </header>
                <footer class="card-bottom">
                    <h2>Très petit gabarit</h2>
                    <p>&lt; 6 kg</p>
                </footer>
            </article>

            <article class="card">
                <header class="card-top">
                    <img src="../src/assets/doge.webp" alt="Petit gabarit" />
                </header>
                <footer class="card-bottom">
                    <h2>Petit gabarit</h2>
                    <p>&lt; 15 kg</p>
                </footer>
            </article>

            <article class="card">
                <header class="card-top">
                    <img src="../src/assets/doge.webp" alt="Gabarit moyen" />
                </header>
                <footer class="card-bottom">
                    <h2>Gabarit moyen</h2>
                    <p>&lt; 25 kg</p>
                </footer>
            </article>

            <article class="card">
                <header class="card-top">
                    <img src="../src/assets/doge.webp" alt="Grand gabarit" />
                </header>
                <footer class="card-bottom">
                    <h2>Grand gabarit</h2>
                    <p>&lt; 40 kg</p>
                </footer>
            </article>

            <article class="card">
                <header class="card-top">
                    <img src="../src/assets/doge.webp" alt="Très grand gabarit" />
                </header>
                <footer class="card-bottom">
                    <h2>Très grand gabarit</h2>
                    <p>&gt; 40 kg</p>
                </footer>
            </article>
        </section>
    </section>
</template>
<style scoped>
#Tarifs {
    background: #03a9f4;
    padding: 60px 16px 80px;
}

.header {
    max-width: 960px;
    margin: 0 auto 40px;
    text-align: center;
    color: #fff;
}

.header p {
    margin: 0;
    font-size: 0.9rem;
    letter-spacing: 0.08em;
    text-transform: uppercase;
    opacity: 0.9;
}

.header h1 {
    margin: 12px 0 0;
    font-size: 2.2rem;
    line-height: 1.1;
}

.tableau {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-auto-rows: 1fr;
    gap: 20px;
    max-width: 960px;
    margin: 0 auto;
}

.card {
    background: #fff;
    border-radius: 14px;
    box-shadow: 0 12px 24px rgba(0, 0, 0, 0.12);
    overflow: hidden;
    display: flex;
    flex-direction: column;
    min-height: 260px;
}

.card-top {
    width: 100%;
    aspect-ratio: 16 / 9;
    overflow: hidden;
}

.card-top img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    display: block;
}

.card-bottom {
    padding: 18px 16px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    text-align: center;
    gap: 6px;
}

.card h2 {
    margin: 0;
    font-size: 1.1rem;
    letter-spacing: 0.04em;
    text-transform: uppercase;
}

.card p {
    margin: 0;
    font-size: 0.95rem;
    color: #333;
}

@media (max-width: 860px) {
    .tableau {
        grid-template-columns: repeat(2, 1fr);
    }
}

@media (max-width: 540px) {
    .tableau {
        grid-template-columns: 1fr;
    }
}
</style>