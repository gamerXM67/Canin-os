<template>
    <section id="Services">
        <p>Services</p>
        <h1>Des Services de Toilettage et de Bien-Être pour Vos Compagnons</h1>
        <p>Offrez à vos animaux de compagnie une expérience de toilettage et de bien-être inégalée. Clara propose des
            services de toilettage professionnels, un accueil chaleureux, et des soins personnalisés pour assurer le
            confort et la sérénité de chaque animal. Que ce soit pour un toilettage complet, des soins réguliers, ou un
            moment de détente, nous mettons tout en œuvre pour que votre compagnon soit entre de bonnes mains.
        </p>
    </section>
    <section class="ServicesSpec">
        <img id="one" src="../src/assets/doge.webp" alt="doge 1"></img>
        <img id="two" src="../src/assets/doge.webp" alt="doge 2"></img>
        <img id="three" src="../src/assets/doge.webp" alt="doge 3"></img>
        <article class="InstaConfort">
            <h2 id="four">Installations Confortables</h2>
            <p>Un espace calme et accueillant, conçu pour le bien-être de votre animal et pour réduire le stress pendant
                les soins.</p>
        </article>
        <article class="SoinToiProff">
            <h2 id="five">Soins de Toilettage Professionnels</h2>
            <p>Des soins complets et personnalisés adaptés aux besoins de chaque race, réalisés avec des produits de
                qualité.</p>
        </article>

        <article class="AttentionPersonnalisee">
            <h2 id="six">Attention Personnalisée pour Chaque Animal</h2>
            <p>Chaque animal est unique et mérite une attention particulière. Clara prend le temps de s'adapter aux
                besoins et aux préférences de votre compagnon.</p>
        </article>
    </section>
</template>
<style scoped>
#Services {
    background-color: #4651cbf0;
    text-align: center;
}

.ServicesSpec {
    background-color: #818cd9;
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    grid-template-rows: repeat(2, auto);
    gap: 20px;
    text-align: center;
    padding: 20px;
}

.ServicesSpec img {
    width: 100%;
    height: auto;
    object-fit: cover;
    display: block;
    border-radius: 8px;
}

#one,
#two,
#three {
    background-color: #3f51b5;
    color: white;
}

.InstaConfort,
.SoinToiProff,
.AttentionPersonnalisee {
    background-color: #3f51b5;
    color: white;
    padding: 20px;
    border-radius: 8px;
}
</style>