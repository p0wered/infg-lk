<script setup lang="ts">

</script>

<template>
  <div class="outer-box">
    <div class="inner-box">
      <div class="title">
        <h4>Вход</h4>
        <p>Введите номер телефона, который указывали при регистрации</p>
      </div>
      <div>
        <div>

        </div>
        <input placeholder="000-000-0000">
      </div>
      <p>
        Продолжая, вы соглашаетесь с <a>политикой обработки ПД</a> и <a>согласием на обработку ПД</a>
      </p>
    </div>
  </div>
</template>

<style scoped>
  .outer-box{
    width: 100%;
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .inner-box{
    padding: 1.25rem;
    border-radius: 12px;
    box-shadow: 0 4px 12px rgba(0, 0, 0, 0.12);
  }
  .title{
    display: flex;
    gap: 8px;
    flex-direction: column;
    text-align: center;
  }
  .title p{
    color: var(--content-secondary)
  }
</style>