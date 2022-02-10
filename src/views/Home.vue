<template>
    <div class="home">
        <home-hero></home-hero>
        <campaign-cards></campaign-cards>
        testtt
            <stripe-checkout
      ref="checkoutRef"
      mode="payment"
      :pk="publishableKey"
      :line-items="lineItems"
      :success-url="successURL"
      :cancel-url="cancelURL"
      @loading="v => loading = v"
    />
        </div>
    </div>
</template>

<script>
import HomeHero from '@/components/HomeHero.vue';
import CampaignCards from '@/components/CampaignCards';
import { StripeCheckout } from '@vue-stripe/vue-stripe';

export default {
    name: 'Home',
    components: {
        HomeHero,
        CampaignCards,
        StripeCheckout
    }
,
  data () {
    this.publishableKey = "";
    return {
      loading: false,
      lineItems: [
        {
          price: 'some-price-id', // The id of the one-time price you created in your Stripe dashboard
          quantity: 1,
        },
      ],
      successURL: 'your-success-url',
      cancelURL: 'your-cancel-url',
    };
  },
  // You will be redirected to Stripe's secure checkout page
  submit () {
    this.$refs.checkoutRef.redirectToCheckout();
  },
};
</script>
