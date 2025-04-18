<script setup lang="ts">
  import SvgNotificationUnread from "../icons/SvgNotificationUnread.vue";
  import CreditCard from "../components/CreditCard.vue";
</script>

<template>
  <div class="container" style="padding: 2vw">
    <div class="heading-box">
      <div class="heading">
        <div>
          <p class="md-text" style="margin-bottom: 6px">Иван Иванович</p>
          <p class="xs-text">Добро пожаловать!</p>
        </div>
        <div class="btn-layout">
          <div class="btn-notifications flex-center">
            <SvgNotificationUnread/>
          </div>
          <div class="profile-picture flex-center">
            <img src="../assets/img/pfp.png" alt="pfp">
          </div>
        </div>
      </div>
      <div>
        <p class="xs-text" style="margin: 0 0 10px 16px">Мои способы оплаты</p>
        <div class="card-list-container">
          <div class="card-list">
            <CreditCard/>
            <CreditCard/>
            <CreditCard/>
            <CreditCard/>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
  .heading-box{
    display: flex;
    flex-direction: column;
    gap: 22px;
    background-color: var(--secondary-300);
    border-radius: 32px;
    background-image: url('../assets/img/Line.svg');
    background-repeat: no-repeat;
    background-position: calc(97% + 120px) -91px;
    overflow: hidden;
  }

  .heading{
    display: flex;
    justify-content: space-between;
    padding: 24px 16px 0 16px;
  }

  .btn-layout{
    display: flex;
    align-items: center;
    gap: 16px;
  }

  .btn-notifications{
    width: 48px;
    height: 48px;
    border-radius: 16px;
    border: 2px solid var(--content-dark);
    background-color: var(--secondary-300);
  }

  .profile-picture{
    width: 60px;
    height: 60px;
    background-color: var(--content-dark);
    border-radius: 16px;
  }

  .profile-picture img{
    width: 48px;
    height: 48px;
    border-radius: 12px;
  }

  .card-list-container {
    width: 100%;
    overflow-x: auto;
    -webkit-overflow-scrolling: touch;
  }

  .card-list {
    display: flex;
    padding-bottom: 24px;
    min-width: min-content;
  }

  .card-list-container::-webkit-scrollbar {
    display: none;
  }

  .card-list-container {
    -ms-overflow-style: none;
    scrollbar-width: none;
  }
</style>