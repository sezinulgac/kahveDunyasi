<template>
  <div class="cart-header" style="background-color: #F7F8F9; padding: 20px;">
    <div style="display: flex; align-items: center; justify-content: center;">
      <img src="../assets/images/cargo-car.png" alt="Kargo Arabası" style="max-width: 32px; max-height: 20px;">
      <div style="margin-left: 20px;">
        <strong style="font-size: 13px; color: #005e5c; font-family: Gotham-Bold, sans-serif; margin: 0;">
          500 TL VE ÜZERİ KARGO BEDAVA
        </strong>
      </div>
    </div>
  </div>
</template>


<!-- ... -->


<script lang="ts">
import { defineComponent, ref } from 'vue';

export default defineComponent({
  name: 'CartHeader',
  props: {
    totalPrice: {
      type: Number,
      required: true,
    },
  },
  setup(props) {
    // Örnek bir bedava kargo eşik değeri, istediğiniz değere göre güncelleyebilirsiniz.
    const freeShippingThreshold = 500;
    // Kargo bedava durumu kontrolü
    const freeShipping = ref(props.totalPrice >= freeShippingThreshold);

    return {
      freeShipping,
    };
  },
});
</script>

<style scoped>
.cart-header {
  /* Stilize edilebilir */
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  height: 60px; /* Örnekteki yüksekliği istediğiniz gibi ayarlayabilirsiniz */
}
</style>
