<template>
    <div class="home">
        <home-hero></home-hero>
        <campaign-cards></campaign-cards>
        testtt
        <div>
            <stripe-element-card />
        </div>
    </div>
</template>

<script>
import HomeHero from '@/components/HomeHero.vue';
import CampaignCards from '@/components/CampaignCards';
import { StripeElementCard } from '@vue-stripe/vue-stripe';

export default {
    name: 'Home',
    components: {
        HomeHero,
        CampaignCards,
        StripeElementCard
    }
};
</script>
