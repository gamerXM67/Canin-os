<template>
    <section id="Contact">
        <section id="contact-info">
            <div class="info-card">
                <div class="icon">📍</div>
                <div class="content">
                    <h3>Localisation</h3>
                    <p>127 Bis Avenue des Canards Enrhumés, 67420<br>Niederschaeffolsheim</p>
                </div>
            </div>
            <div class="info-card">
                <div class="icon">📞</div>
                <div class="content">
                    <h3>Téléphone</h3>
                    <p>06 74 20 48 69</p>
                </div>
            </div>
            <div class="info-card">
                <div class="icon">✉️</div>
                <div class="content">
                    <h3>Email</h3>
                    <p>ce.compte.epic@gmail.com</p>
                </div>
            </div>
        </section>
        <p>ça contact ici</p>
        <h1>Contactez-moi</h1>
        <h4>Vous avez des questions ou des préoccupations ? N'hésitez pas à me contacter.</h4>
        <section id="formulaire">
            <input placeholder="votre nom" type="text">
            <input placeholder="votre prénom" type="text">
            <input placeholder="Email" type="email">
            <input placeholder="Numero de téléphone" type="tel" inputmode="numeric">
            <textarea placeholder="Votre message"></textarea>
            <button type="submit">Envoyer</button>
        </section>
    </section>
</template>
<style scoped>
#Contact {
    background-color: #455A64;
}

#contact-info {
    display: flex;
    justify-content: space-around;
    gap: 16px;
    flex-wrap: wrap;
    padding: 20px;
}

.info-card {
    display: flex;
    align-items: center;
    gap: 12px;
    padding: 16px 18px;
    min-width: 220px;
    max-width: 300px;
    background: #ffffff;
    border-radius: 14px;
    box-shadow: 0 6px 14px rgba(0, 0, 0, 0.12);
    color: #1c242e;
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
</style>