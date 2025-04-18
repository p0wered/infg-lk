<script setup lang="ts">
import {defineProps} from "vue";

const props = defineProps({
  bankName: {
    type: String,
    default: 'Bank'
  },
  paymentSystem: {
    type: String,
    default: 'VISA'
  },
  cardNumber: {
    type: String,
    default: '0000 00×× ×××× 0000'
  },
})
</script>

<template>
  <div class="card-layout">
    <div class="heading">
      <div>
        <p class="xs-text" style="margin-bottom: 6px">{{bankName}}</p>
        <p class="xxs-text">{{paymentSystem}}</p>
      </div>
      <div class="bank-logo"/>
    </div>
    <div class="card-number">
      <p>0000 00×× ×××× 0000</p>
    </div>
  </div>
</template>

<style scoped>
  .card-layout {
    position: relative;
    overflow: hidden;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    width: 283px;
    height: 200px;
    border-radius: 20px;
    border: 1px solid var(--content-dark);
    box-shadow: 3px 3px 0 0 var(--primary-500);
    background: var(--primary-700);
    padding: 16px;
    margin-left: 16px;
    margin-right: 2px;
  }

  .card-layout:before, .card-layout:after {
    content: '';
    position: absolute;
    border-radius: 50%;
    border: 2px solid #fbfe4e;
    width: 220px;
    height: 220px;
    z-index: 0;
  }

  .card-layout:before {
    top: -80px;
    left: -85px;
  }

  .card-layout:after {
    top: -130px;
    left: -40px;
  }

  .card-layout p{
    color: #FFDDCCFF;
  }

  .heading{
    display: flex;
    justify-content: space-between;
  }

  .card-number {
    padding: 6px;
    border-radius: 10px;
    background-color: rgba(255, 255, 255, 0.12);
    width: fit-content;
  }

  .bank-logo{
    width: 48px;
    height: 48px;
    background-color: #fbfe4e;
    border-radius: 10px;
    border: 1px solid var(--content-dark);
  }
</style>