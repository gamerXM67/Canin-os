<script setup lang="ts">
import { ref } from 'vue'

const faqs = [
    {
        question: "Acceptez-vous les chiens de catégorie ?",
        answer: "Oui j'accepte les chiens de catégorie.Je bénéficie même de la formation de détendeur de chien de catégorie 1 et 2.",
    },
    {
        question: "Le maître peut-il rester avec lors du toilettage ?",
        answer: "Oui le maître peut rester avec si le chien reste en place car certain loulou en voyant la présence du maître peut ne pas ce laisser faire. Pour une question de sécurité il est préférable que le maître ne soit alors pas avec.",
    },
    {
        question: "Acceptez-vous tout type de chien et chat ?",
        answer: "Qu'importe la taille tout chien et chat sont acceptés.",
    },
    {
        question: "Quels sont les moyens de paiement acceptés ?",
        answer: "J'accepte les paiements par espèce, chèque, PayPal, Paylib, Lifpay ou virement bancaire en instantané.",
    },
    {
        question: "Quels produits utilisez-vous pour le toilettage ?",
        answer: "J'utilise la gamme Petux qui est une gamme vegan et eco responsable.",
    },
    {
        question: "Que sont les Fleurs de Bach ?",
        answer: "Les Fleurs de Bach Velbecia sont fabriquées en France selon la méthode du Dr Bach et pour le bien-être de nos animaux. Ces élixirs floraux permettent d'agir et de rééquilibrer le système émotionnel des petits comme des grands animaux. Chaque formule est liée à un trouble précis et se compose d'une synergie de fleurs.",
    },
    {
        question: "Quelle est la composition des Fleurs de Bach ?",
        answer: "Les Fleurs de Bach ne contiennent ni gluten ni allergène. Ingrédients : Eau, Extrait d'arôme de sirop d'érable, Extraits de fleurs de Bach.",
    },
    {
        question: "Proposez-vous d'autres produits à la vente ?",
        answer: "Oui, je propose à la vente des croquettes, des friandises ainsi que des produits d'entretien du poil pour prendre soin de vos animaux entre les séances de toilettage.",
    },
]

const openIndex = ref<number | null>(null)

function toggle(index: number) {
    openIndex.value = openIndex.value === index ? null : index
}
</script>

<template>
    <section id="Faq">
        <div class="container">
            <header class="header">
                <span class="badge">FAQ</span>
                <h1>Questions Fréquemment Posées</h1>
            </header>

            <div class="faq-list">
                <article v-for="(item, index) in faqs" :key="index" class="faq-item">
                    <button class="faq-header" :class="{ 'is-active': openIndex === index }" type="button"
                        @click="toggle(index)">
                        <span class="question">{{ item.question }}</span>
                        <span class="icon" :class="{ rotate: openIndex === index }">
                            <svg width="12" height="12" viewBox="0 0 12 12" fill="none"
                                xmlns="http://www.w3.org/2000/svg">
                                <path d="M2 4L6 8L10 4" stroke="currentColor" stroke-width="2" stroke-linecap="round"
                                    stroke-linejoin="round" />
                            </svg>
                        </span>
                    </button>

                    <transition name="slide-fade">
                        <div v-if="openIndex === index" class="faq-content">
                            <p>{{ item.answer }}</p>
                        </div>
                    </transition>
                </article>
            </div>
        </div>
    </section>
</template>

<style scoped>
#Faq {
    padding: 100px 20px;
}

.container {
    max-width: 800px;
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
    margin: 0;
}

.faq-list {
    display: flex;
    flex-direction: column;
    gap: 16px;
}

.faq-item {
    background: rgba(255, 255, 255, 0.5);
    border-radius: 20px;
    border: 1px solid rgba(255, 255, 255, 0.6);
    box-shadow: 0 4px 15px rgba(0, 0, 0, 0.02);
    overflow: hidden;
    transition: all 0.3s ease;
}

.faq-item:hover {
    background: rgba(255, 255, 255, 0.8);
    transform: translateX(5px);
}

.faq-header {
    padding: 20px 25px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    cursor: pointer;
    width: 100%;
    background: transparent;
    border: none;
    text-align: left;
    transition: all 0.3s ease;
}

.question {
    font-size: 1.1rem;
    font-weight: 600;
    color: #2c3e50;
}

.icon {
    color: #dc8c82;
    transition: transform 0.3s ease;
}

.icon.rotate {
    transform: rotate(180deg);
}

.faq-header.is-active {
    background: rgba(220, 140, 130, 0.05);
}

.faq-content {
    padding: 0 25px 25px 25px;
    color: #666;
    line-height: 1.6;
    font-size: 1rem;
}

.faq-content p {
    margin: 0;
    border-top: 1px solid rgba(0, 0, 0, 0.05);
    padding-top: 15px;
}

/* Transitions Vue pour l'ouverture fluide de l'accordéon */
.slide-fade-enter-active {
    transition: all 0.3s ease-out;
}

.slide-fade-leave-active {
    transition: all 0.2s cubic-bezier(1, 0.5, 0.8, 1);
}

.slide-fade-enter-from,
.slide-fade-leave-to {
    transform: translateY(-10px);
    opacity: 0;
}

@media (max-width: 600px) {
    h1 {
        font-size: 1.8rem;
    }

    .question {
        font-size: 1rem;
    }

    .faq-item:hover {
        transform: none;
    }
}
</style>