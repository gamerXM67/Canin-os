<template>
    <section id="Contact">
        <div class="container">
            <header class="header">
                <span class="badge">Contact</span>
                <h1>Contactez-moi</h1>
                <p class="subtitle">Vous avez des questions ou des préoccupations ? N'hésitez pas à me contacter.</p>
            </header>

            <address id="contact-info">
                <article class="info-card">
                    <span class="icon" aria-hidden="true">📍</span>
                    <div class="content">
                        <h3>Localisation</h3>
                        <p>127 Bis Avenue des Canards Enrhumés<br>67420 Niederschaeffolsheim</p>
                    </div>
                </article>

                <article class="info-card">
                    <span class="icon" aria-hidden="true">📞</span>
                    <div class="content">
                        <h3>Téléphone</h3>
                        <p>06 74 20 48 69</p>
                    </div>
                </article>

                <article class="info-card">
                    <span class="icon" aria-hidden="true">✉️</span>
                    <div class="content">
                        <h3>Email</h3>
                        <p>ce.compte.epic@gmail.com</p>
                    </div>
                </article>
            </address>

            <article id="form-container">
                <form id="formulaire" @submit.prevent>
                    <div class="input-group">
                        <label for="nom" class="sr-only">Votre nom</label>
                        <input id="nom" placeholder="Votre nom" type="text" required>

                        <label for="prenom" class="sr-only">Votre prénom</label>
                        <input id="prenom" placeholder="Votre prénom" type="text" required>
                    </div>

                    <div class="input-group">
                        <label for="email" class="sr-only">Email</label>
                        <input id="email" placeholder="Email" type="email" autocomplete="email" required>

                        <label for="telephone" class="sr-only">Téléphone</label>
                        <input id="telephone" placeholder="Téléphone" type="tel" inputmode="numeric">
                    </div>

                    <label for="message" class="sr-only">Votre message</label>
                    <textarea id="message" placeholder="Comment puis-je aider votre compagnon ?" required></textarea>

                    <button id="envoie" type="submit">Envoyer le message</button>
                </form>
            </article>
        </div>
    </section>
</template>

<style scoped>
#Contact {
    padding: 100px 20px;
}

.container {
    max-width: 1100px;
    margin: 0 auto;
}

.header {
    text-align: center;
    margin-bottom: 50px;
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
    margin: 0 0 15px;
}

.subtitle {
    color: #6a6a6a;
    font-size: 1.1rem;
    max-width: 600px;
    margin: 0 auto;
}

/* Classe pour cacher les labels tout en restant lisibles par les lecteurs d'écran */
.sr-only {
    position: absolute;
    width: 1px;
    height: 1px;
    padding: 0;
    margin: -1px;
    overflow: hidden;
    clip: rect(0, 0, 0, 0);
    border: 0;
}

#contact-info {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 20px;
    margin-bottom: 60px;
    font-style: normal;
    /* Annule l'italique par défaut de <address> */
}

.info-card {
    display: flex;
    align-items: center;
    gap: 15px;
    padding: 25px;
    background: rgba(255, 255, 255, 0.5);
    border-radius: 24px;
    border: 1px solid rgba(255, 255, 255, 0.6);
    box-shadow: 0 10px 30px rgba(0, 0, 0, 0.03);
    transition: transform 0.3s ease;
}

.info-card:hover {
    transform: translateY(-5px);
    background: rgba(255, 255, 255, 0.8);
}

.info-card .icon {
    font-size: 1.8rem;
    background: white;
    width: 55px;
    height: 55px;
    display: grid;
    place-items: center;
    border-radius: 18px;
    box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
}

.info-card h3 {
    margin: 0 0 5px;
    font-size: 1.1rem;
    color: #2c3e50;
}

.info-card p {
    margin: 0;
    font-size: 0.95rem;
    color: #6a6a6a;
    line-height: 1.4;
}

#form-container {
    background: rgba(255, 255, 255, 0.5);
    padding: 40px;
    border-radius: 30px;
    max-width: 800px;
    margin: 0 auto;
    border: 1px solid rgba(255, 255, 255, 0.6);
    box-shadow: 0 15px 35px rgba(0, 0, 0, 0.03);
}

#formulaire {
    display: flex;
    flex-direction: column;
    gap: 15px;
}

.input-group {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 15px;
}

input,
textarea {
    padding: 15px 20px;
    border-radius: 15px;
    border: 1px solid rgba(220, 140, 130, 0.2);
    background: white;
    font-size: 1rem;
    transition: all 0.3s ease;
    outline: none;
}

input:focus,
textarea:focus {
    border-color: #dc8c82;
    /* Halo lumineux pour indiquer le focus utilisateur */
    box-shadow: 0 0 0 4px rgba(220, 140, 130, 0.1);
}

#message {
    min-height: 150px;
    resize: vertical;
}

#envoie {
    padding: 16px;
    background-color: #dc8c82;
    color: white;
    border: none;
    border-radius: 30px;
    font-weight: 700;
    font-size: 1.1rem;
    cursor: pointer;
    transition: all 0.3s ease;
    box-shadow: 0 6px 20px rgba(220, 140, 130, 0.3);
    margin-top: 10px;
}

#envoie:hover {
    background-color: #ca7b71;
    transform: translateY(-3px);
    box-shadow: 0 10px 25px rgba(220, 140, 130, 0.4);
}

@media (max-width: 880px) {
    #contact-info {
        grid-template-columns: 1fr;
    }

    .input-group {
        grid-template-columns: 1fr;
    }

    #form-container {
        padding: 20px;
    }
}
</style>