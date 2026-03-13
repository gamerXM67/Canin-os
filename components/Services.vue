<template>
    <section class="services-wrapper">
        <header id="Services" class="container">
            <span class="badge">Prestations</span>
            <h1>Des Services de Toilettage et de Bien-Être pour Vos Compagnons</h1>

            <article class="intro-bubble">
                <p class="services-intro">
                    Offrez à vos animaux de compagnie une expérience de toilettage et de bien-être inégalée.
                    Nous proposons des services professionnels, un accueil chaleureux et des soins personnalisés
                    pour assurer le confort et la sérénité de chaque animal.
                </p>
            </article>
        </header>

        <section class="ServicesSpec">
            <article class="service-card">
                <figure>
                    <img id="one" src="../src/assets/doge.webp" alt="Installations">
                </figure>
                <div class="card-text">
                    <h2>Installations Confortables</h2>
                    <p>Un espace calme et accueillant, conçu pour réduire le stress pendant les soins.</p>
                </div>
            </article>

            <article class="service-card">
                <figure>
                    <img id="two" src="../src/assets/dogeSoins.webp" alt="Toilettage">
                </figure>
                <div class="card-text">
                    <h2>Soins Professionnels</h2>
                    <p>Des soins complets adaptés à chaque race, réalisés avec des produits de haute qualité.</p>
                </div>
            </article>

            <article class="service-card">
                <figure>
                    <img id="three" src="../src/assets/dogeAttention.webp" alt="Attention">
                </figure>
                <div class="card-text">
                    <h2>Attention Personnalisée</h2>
                    <p>Chaque animal est unique. Nous prenons le temps nécessaire pour chaque loulou.</p>
                </div>
            </article>
        </section>
    </section>
</template>

<style scoped>
.container {
    max-width: 1000px;
    margin: 0 auto;
    text-align: center;
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
    font-size: 2.4rem;
    color: #2c3e50;
    margin-bottom: 30px;
}

.intro-bubble {
    background: rgba(255, 255, 255, 0.5);
    padding: 30px 40px;
    border-radius: 24px;
    border: 1px solid rgba(255, 255, 255, 0.6);
    box-shadow: 0 10px 30px rgba(0, 0, 0, 0.03);
    max-width: 800px;
    margin: 0 auto 60px auto;
}

.services-intro {
    font-size: 1.1rem;
    color: #5a5a5a;
    line-height: 1.7;
    margin: 0;
}

.ServicesSpec {
    max-width: 1200px;
    margin: 0 auto;
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 30px;
    padding: 0 20px;
}

.service-card {
    background: rgba(255, 255, 255, 0.5);
    border-radius: 24px;
    overflow: hidden;
    box-shadow: 0 10px 30px rgba(0, 0, 0, 0.03);
    border: 1px solid rgba(255, 255, 255, 0.6);
    transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.service-card:hover {
    /* Effet d'élévation au survol */
    transform: translateY(-10px);
    box-shadow: 0 20px 40px rgba(0, 0, 0, 0.08);
}

figure {
    margin: 0;
}

.service-card img {
    width: 100%;
    height: 220px;
    object-fit: cover;
    display: block;
}

.card-text {
    padding: 25px;
    text-align: center;
}

.card-text h2 {
    font-size: 1.3rem;
    color: #2c3e50;
    margin-bottom: 12px;
}

.card-text p {
    font-size: 0.95rem;
    color: #6a6a6a;
    line-height: 1.5;
}

@media (max-width: 992px) {
    .ServicesSpec {
        grid-template-columns: repeat(2, 1fr);
    }
}

@media (max-width: 600px) {
    .ServicesSpec {
        grid-template-columns: 1fr;
    }

    h1 {
        font-size: 1.8rem;
    }

    .intro-bubble {
        padding: 20px;
    }
}
</style>