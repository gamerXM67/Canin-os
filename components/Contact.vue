<template>
    <section id="Contact">
        <section id="contact-info">
            <article class="info-card">
                <span class="icon">📍</span>
                <section class="content">
                    <h3>Localisation</h3>
                    <p>127 Bis Avenue des Canards Enrhumés, 67420<br>Niederschaeffolsheim</p>
                </section>
            </article>
            <article class="info-card">
                <span class="icon">📞</span>
                <section class="content">
                    <h3>Téléphone</h3>
                    <p>06 74 20 48 69</p>
                </section>
            </article>
            <article class="info-card">
                <span class="icon">✉️</span>
                <section class="content">
                    <h3>Email</h3>
                    <p>ce.compte.epic@gmail.com</p>
                </section>
            </article>
        </section>
        <p>ça contact ici</p>
        <h1>Contactez-moi</h1>
        <h4>Vous avez des questions ou des préoccupations ? N'hésitez pas à me contacter.</h4>
        <section id="formulaire">
            <input id="nom" placeholder="votre nom" type="text">
            <input id="prenom" placeholder="votre prénom" type="text">
            <input id="email" placeholder="Email" type="email" autocomplete="email">
            <input id="telephone" placeholder="Numero de téléphone" type="tel" inputmode="numeric">
            <textarea id="message" placeholder="Votre message"></textarea>
            <button id="envoie" type="submit">Envoyer</button>
        </section>
    </section>
</template>
<style scoped>
#Contact {
    background-color: #455A64;
}

#contact-info {
    display: grid;
    grid-template-columns: repeat(3, minmax(260px, 1fr));
    gap: 18px;
    padding: 24px 0;

    /* align like on the screenshot */
    max-width: 1140px;
    margin: 0 auto;
}

.info-card {
    display: flex;
    align-items: center;
    gap: 14px;
    padding: 18px 20px;
    background: #fff;
    border-radius: 16px;
    box-shadow: 0 10px 22px rgba(0, 0, 0, 0.08);
    color: #1c242e;
}

@media (max-width: 880px) {
    #contact-info {
        grid-template-columns: 1fr;
    }

    .info-card {
        max-width: 620px;
        margin: 0 auto;
    }
}


.info-card .icon {
    display: grid;
    place-items: center;
    width: 54px;
    height: 54px;
    border-radius: 50%;
    background: rgba(255, 255, 255, 0.55);
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.12);
    font-size: 1.5rem;
}

.info-card .content h3 {
    margin: 0 0 4px;
    font-size: 1rem;
    font-weight: 600;
}

.info-card .content p {
    margin: 0;
    font-size: 0.9rem;
    line-height: 1.3;
}

#formulaire {
    display: grid;
    grid-template-columns: 2fr 2fr;
    gap: 12px;
    max-width: 480px;
    margin: 24px auto;
}

#message {
    grid-column: 1 / 3;
    grid-row: 3;
}

#envoie {
    grid-column: 1 / 3;
    grid-row: 4;
    padding: 10px 20px;
    background-color: #0070f3;
    color: white;
    border: none;
    border-radius: 4px;
    cursor: pointer;
}
</style>