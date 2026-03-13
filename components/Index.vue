<template>
    <main id="Index">
        <section id="hero">
            <article class="hero-content">
                <h1>Bienvenue au salon de toilettage <span class="brand-name">Pattes à l'eau</span></h1>
                <p class="hero-subtitle">Prendre soin de vos animaux avec compétence et professionnalisme</p>
                <p class="hero-description">
                    Au salon de toilettage Pattes à l'eau, nous offrons des soins complets et attentionnés pour vos
                    animaux.
                    Nous veillons à leur bien-être en leur apportant un toilettage de qualité dans un environnement
                    apaisant.
                </p>

                <nav class="bouttonEntrer" aria-label="Actions principales">
                    <a class="btn btnSaPlus" href="#Presentation">En savoir plus</a>
                    <a class="btn btnContact" href="#Contact">Nous contacter</a>
                </nav>
            </article>
        </section>
    </main>
</template>

<style scoped>
#Index {
    background: linear-gradient(180deg, #f6feff 0%, #ebf4ff 100%);
    min-height: 80vh;
    display: flex;
    align-items: center;
    justify-content: center;
}

#hero {
    padding: 80px 20px;
    max-width: 1000px;
    margin: 0 auto;
    text-align: center;
}

.hero-content {
    background: rgba(255, 255, 255, 0.5);
    padding: 40px;
    border-radius: 24px;
    box-shadow: 0 10px 30px rgba(0, 0, 0, 0.05);
}

h1 {
    font-size: 2.8rem;
    color: #2c3e50;
    margin-bottom: 16px;
    line-height: 1.2;
}

.brand-name {
    color: #dc8c82;
    font-weight: 800;
}

.hero-subtitle {
    font-size: 1.4rem;
    font-weight: 600;
    color: #4a4a4a;
    margin-bottom: 24px;
}

.hero-description {
    font-size: 1.1rem;
    color: #6a6a6a;
    line-height: 1.6;
    max-width: 700px;
    margin: 0 auto 40px auto;
}

.bouttonEntrer {
    display: flex;
    justify-content: center;
    gap: 20px;
    flex-wrap: wrap;
}

.bouttonEntrer .btn {
    padding: 14px 30px;
    border-radius: 30px;
    text-decoration: none;
    font-weight: 700;
    cursor: pointer;
    transition: all 250ms ease;
    min-width: 200px;
    text-align: center;
    border: 2px solid transparent;
    font-size: 1rem;
}

.bouttonEntrer .btn:hover {
    /* Translation verticale pour l'effet de levier au survol */
    transform: translateY(-3px);
    box-shadow: 0 12px 20px rgba(220, 140, 130, 0.2);
}

.bouttonEntrer .btnSaPlus {
    background-color: #dc8c82;
    color: #ffffff;
    box-shadow: 0 6px 15px rgba(220, 140, 130, 0.3);
}

.bouttonEntrer .btnSaPlus:hover {
    background-color: #ca7b71;
}

.bouttonEntrer .btnContact {
    background-color: transparent;
    border-color: #dc8c82;
    color: #dc8c82;
}

.bouttonEntrer .btnContact:hover {
    background-color: rgba(220, 140, 130, 0.1);
}

@media (max-width: 768px) {
    h1 {
        font-size: 2rem;
    }

    .hero-subtitle {
        font-size: 1.2rem;
    }

    .hero-content {
        padding: 20px;
    }

    .bouttonEntrer {
        gap: 10px;
    }

    .bouttonEntrer .btn {
        width: 100%;
    }
}
</style>