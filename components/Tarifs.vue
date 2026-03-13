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
                    <div class="card-bottom">
                        <h2>Chats</h2>
                        <ul class="price-list">
                            <li><span>Brossage / retaillage</span> <span class="price">dès 30€</span></li>
                            <li><span>Bain / séchage / brossage</span> <span class="price">dès 40€</span></li>
                            <li><span>Tonte complète</span> <span class="price">dès 40€</span></li>
                        </ul>
                    </div>
                </article>

                <article class="card">
                    <figure class="card-top">
                        <img src="../src/assets/dogeTresPetit.webp" alt="Chien très petit gabarit" />
                    </figure>
                    <div class="card-bottom">
                        <h2>Très petit <span class="weight-tag">moins de 6kg</span></h2>
                        <ul class="price-list">
                            <li><span>Bain, brushing, retaillage</span> <span class="price">dès 30€</span></li>
                            <li><span>Tonte complète</span> <span class="price">dès 45€</span></li>
                            <li><span>Épilation</span> <span class="price">dès 55€</span></li>
                        </ul>
                    </div>
                </article>

                <article class="card">
                    <figure class="card-top">
                        <img src="../src/assets/dogePetit.webp" alt="Chien petit gabarit" />
                    </figure>
                    <div class="card-bottom">
                        <h2>Petit <span class="weight-tag">entre 6 et 15kg</span></h2>
                        <ul class="price-list">
                            <li><span>Bain, brushing, retaillage</span> <span class="price">dès 30€</span></li>
                            <li><span>Tonte complète</span> <span class="price">dès 45€</span></li>
                            <li><span>Épilation</span> <span class="price">dès 55€</span></li>
                        </ul>
                    </div>
                </article>

                <article class="card">
                    <figure class="card-top">
                        <img src="../src/assets/dogeMoyen.webp" alt="Chien gabarit moyen" />
                    </figure>
                    <div class="card-bottom">
                        <h2>Moyen <span class="weight-tag">entre 15 et 25kg</span></h2>
                        <ul class="price-list">
                            <li><span>Bain, brushing, retaillage</span> <span class="price">dès 55€</span></li>
                            <li><span>Tonte complète</span> <span class="price">dès 65€</span></li>
                            <li><span>Coupe ciseaux</span> <span class="price">dès 75€</span></li>
                            <li><span>Épilation</span> <span class="price">dès 85€</span></li>
                        </ul>
                    </div>
                </article>

                <article class="card">
                    <figure class="card-top">
                        <img src="../src/assets/dogeGrand.webp" alt="Chien grand gabarit" />
                    </figure>
                    <div class="card-bottom">
                        <h2>Grand <span class="weight-tag">entre 25 et 40kg</span></h2>
                        <ul class="price-list">
                            <li><span>Poils courts (Labrador...)</span> <span class="price">dès 45€</span></li>
                            <li><span>Poils longs (Australien...)</span> <span class="price">dès 65€</span></li>
                            <li><span>Nordiques (Husky...)</span> <span class="price">45€/h</span></li>
                        </ul>
                    </div>
                </article>

                <article class="card">
                    <figure class="card-top">
                        <img src="../src/assets/dogeTresGrand.webp" alt="Chien très grand gabarit" />
                    </figure>
                    <div class="card-bottom">
                        <h2>Très grand <span class="weight-tag">plus de 40kg</span></h2>
                        <div class="special-price">
                            <span class="main-price">50€ <small>/ l'heure</small></span>
                            <p class="description">Terre Neuve, Saint-Bernard et gabarits XXL</p>
                        </div>
                    </div>
                </article>
            </div>
        </div>
    </section>
</template>

<style scoped>
#Tarifs {
    padding: 100px 20px;
    background: linear-gradient(180deg, #f6feff 0%, #ebf4ff 100%);
}

.container {
    max-width: 1200px;
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
    padding: 6px 18px;
    border-radius: 50px;
    font-size: 0.8rem;
    font-weight: 700;
    text-transform: uppercase;
    letter-spacing: 1px;
    margin-bottom: 15px;
}

.header h1 {
    font-size: 2.6rem;
    color: #2c3e50;
    margin: 0;
    font-weight: 800;
}

.tableau {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-auto-rows: 1fr;
    gap: 30px;
}

.card {
    background: rgba(255, 255, 255, 0.6);
    backdrop-filter: blur(10px);
    border-radius: 30px;
    border: 1px solid rgba(255, 255, 255, 0.8);
    box-shadow: 0 15px 35px rgba(0, 0, 0, 0.05);
    overflow: hidden;
    transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
    display: flex;
    flex-direction: column;
}

.card:hover {
    transform: translateY(-10px);
    box-shadow: 0 25px 50px rgba(0, 0, 0, 0.1);
    background: rgba(255, 255, 255, 0.95);
}

.card-top {
    width: 100%;
    aspect-ratio: 16 / 10;
    margin: 0;
}

.card-top img {
    width: 100%;
    height: 100%;
    object-fit: cover;
}

.card-bottom {
    padding: 30px 25px;
    flex-grow: 1;
    display: flex;
    flex-direction: column;
}

.card h2 {
    margin: 0 0 20px;
    font-size: 1.3rem;
    color: #2c3e50;
    font-weight: 800;
    text-transform: uppercase;
    display: flex;
    flex-direction: column;
    gap: 5px;
}

.weight-tag {
    font-size: 0.75rem;
    color: #dc8c82;
    font-weight: 600;
    letter-spacing: 0.5px;
}

.price-list {
    list-style: none;
    padding: 0;
    margin: 0;
    display: flex;
    flex-direction: column;
    gap: 12px;
}

.price-list li {
    display: flex;
    justify-content: space-between;
    align-items: center;
    font-size: 0.95rem;
    color: #5a5a5a;
    border-bottom: 1px dashed rgba(0, 0, 0, 0.1);
    padding-bottom: 8px;
}

.price {
    color: #dc8c82;
    font-weight: 800;
    white-space: nowrap;
    font-size: 1.05rem;
    padding-left: 10px;
}

/* Style spécifique pour la dernière carte */
.special-price {
    margin: auto 0;
    text-align: center;
}

.main-price {
    font-size: 2rem;
    color: #dc8c82;
    font-weight: 900;
    display: block;
}

.main-price small {
    font-size: 0.9rem;
    color: #5a5a5a;
    font-weight: 500;
}

.description {
    font-size: 0.9rem;
    color: #7f8c8d;
    margin-top: 10px;
    line-height: 1.4;
}

@media (max-width: 1024px) {
    .tableau {
        grid-template-columns: repeat(2, 1fr);
    }
}

@media (max-width: 650px) {
    .tableau {
        grid-template-columns: 1fr;
    }

    .header h1 {
        font-size: 2rem;
    }

    .card-bottom {
        padding: 20px;
    }
}
</style>