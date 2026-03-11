<script setup lang="ts">
import { ref } from 'vue'

const faqs = [
    {
        question: 'Acceptez-vous les chiens de catégorie ?',
        answer:
            'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.',
    },
    {
        question: 'Le maître peut-il rester avec lors du toilettage ?',
        answer:
            'Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.',
    },
    {
        question: 'Acceptez-vous tout type de chien et chat ?',
        answer:
            'Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.',
    },
    {
        question: 'Quels sont les moyens de paiement acceptés ?',
        answer:
            'Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.',
    },
    {
        question: 'Quels produits utilisez-vous pour le toilettage ?',
        answer:
            'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.',
    },
    {
        question: 'Que sont les Fleurs de Bach ?',
        answer:
            'Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium.',
    },
    {
        question: 'Quelle est la composition des Fleurs de Bach ?',
        answer:
            'Nemo enim ipsam voluptatem quia voluptas sit aspernatur aut odit aut fugit, sed quia consequuntur magni dolores eos.',
    },
    {
        question: "Proposez-vous d'autres produits à la vente ?",
        answer:
            'Neque porro quisquam est, qui dolorem ipsum quia dolor sit amet, consectetur, adipisci velit.',
    },
]

const openIndex = ref<number | null>(null)

function toggle(index: number) {
    openIndex.value = openIndex.value === index ? null : index
}
</script>

<template>
    <section id="Faq">
        <p>Faqs</p>
        <h1>Questions Fréquemment Posées</h1>

        <section v-for="(item, index) in faqs" :key="index" class="Faq-item">
            <div class="faq-header" :class="{ 'is-active': openIndex === index }" @click="toggle(index)">
                <span class="question">{{ item.question }}</span>

                <span class="icon" :class="{ rotate: openIndex === index }">
                    <i class="fas fa-chevron-down"></i>
                </span>
            </div>

            <div v-if="openIndex === index" class="faq-content">
                <p>{{ item.answer }}</p>
            </div>
        </section>
    </section>
</template>

<style scoped>
#Faq {
    background-color: #2E7D32;
    padding: 40px 0;
    display: flex;
    flex-direction: column;
    align-items: center;
}

.Faq-item {
    width: 90%;
    max-width: 600px;
    border-radius: 8px;
    overflow: hidden;
    margin-bottom: 16px;
}

.faq-header {
    padding: 15px 20px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    cursor: pointer;
    font-weight: bold;
    color: #003366;
    background-color: #d4a3a3;
    /* Bleu foncé comme sur ton image */
    border-left: 5px solid transparent;
    /* Prêt pour l'état actif */
}

/* Style quand l'accordéon est ouvert */
.faq-header.is-active {
    border-left: 5px solid #d4a3a3;
    /* La barre rose/rouge à gauche */
}

.icon {
    transition: transform 0.3s ease;
}

.icon.rotate {
    transform: rotate(180deg);
}

.faq-content {
    padding: 15px 20px;
    border-top: 1px solid #eee;
    color: #666;
    background-color: #eee;
    line-height: 1.5;
}
</style>
