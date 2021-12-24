<template>
  <div class="row m-0 order-success">
    <div class="col-12 text-center">
      <h2>Thank you for placing order on Shet.com!</h2>
      <h3>
        Your order Id is: {{ OrderId }},
        <router-link
          :to="{ name: 'Orders' }"
          class="btn btn-primary btn-lg mx-2"
        >
          here</router-link
        >
        to check Order Status.
      </h3>
    </div>
    <DeliveryTruck />
  </div>
</template>

<script>
import DeliveryTruck from '@/components/DeliveryTruck.vue';
export default {
  props: ["OrderId"],
  components: {DeliveryTruck}
};
</script>

<style lang="scss">
.order-success {
  .btn {
    font-size: 2rem;

    &::before {
      content: "Click";

      @media (min-height: 1300px) {
        content: "Tap";
      }
      @media (max-width: 998px) {
        content: "Tap";
      }
    }
  }
}
</style>