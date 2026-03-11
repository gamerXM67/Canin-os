<template>
    <meta charset="UTF-8">
    <link rel="stylesheet" href="assets/css/style.css">

    <body>

        <main id="Index">
            <section id="hero">
                <h1>Bienvenue au salon de toilettage Pattes à l'eau</h1>
                <p>Prendre soin de vos animaux avec compétence et professionnalisme</p>
                <p>Au salon de toilettage Pattes à l'eau, nous offrons des soins complets et attentionnés pour vos
                    animaux. Nous veillons à leur bien-être en leur apportant un toilettage de qualité. </p>
                <div class="bouttonEntrer">
                    <a class="btn btnSaPlus" href="#Presentation">Savoir plus</a>
                    <a class="btn btnContact" href="#Contact">Contact</a>
                </div>
            </section>

        </main>

    </body>
</template>
<style scoped>
#hero {
    background-color: #FB8C00;
    padding-top: 30px;
}


.bouttonEntrer .btn {
    padding: 10px 20px;
    border-radius: 4px;
    text-decoration: none;
    font-weight: 600;
    color: #fff;
}

.bouttonEntrer .btnSaPlus {
    background-color: #0070f3;
}

.bouttonEntrer .btnContact {
    background-color: #333;
}
</style>