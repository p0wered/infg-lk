<script setup lang="ts">
  import SvgNotificationUnread from "../icons/SvgNotificationUnread.vue";
  import CreditCard from "../components/CreditCard.vue";
  import BubbleMoney from "../components/BubbleMoney.vue";
  import BubbleStory from "../components/BubbleStory.vue";
  import NewsItem from "../components/NewsItem.vue";
  import SvgCircleArrowRight from "../icons/SvgCircleArrowRight.vue";
  import ProgressCircle from "../components/ProgressCircle.vue";
</script>

<template>
  <div class="container">
    <div class="">
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
              <CreditCard card-style="blue"/>
              <CreditCard card-style="yellow"/>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class=" bubble-layout">
      <div class="btn-layout" style="padding: 0 16px">
        <div class="gradient-bg">
          <div class="btn-refund flex-center">
            <img src="../assets/img/money-emoji.png" alt="emoji">
            <p class="xs-text">Оформить возврат</p>
          </div>
        </div>
        <div class="history-block">
          <p>Последние списания</p>
          <div class="bubble-list">
            <BubbleMoney :sum=500 :write-off="false"/>
            <BubbleMoney :sum=1999 :write-off="true"/>
            <BubbleMoney :sum=999 :write-off="true"/>
            <BubbleMoney :sum=1500 :write-off="false"/>
            <BubbleMoney :sum=50 :write-off="false"/>
            <BubbleMoney :sum=999 :write-off="true"/>
          </div>
        </div>
      </div>
      <div class="stories-list">
        <BubbleStory title="За что списали?" imgSrc="/src/assets/img/story-1.png"/>
        <BubbleStory title="Преимущества подписки" imgSrc="/src/assets/img/story-2.png"/>
        <BubbleStory title="Мы мошенники?" imgSrc="/src/assets/img/story-3.png"/>
        <BubbleStory title="Безопасность ваших данных" imgSrc="/src/assets/img/story-4.png"/>
        <BubbleStory title="За что списали?" imgSrc="/src/assets/img/story-1.png"/>
      </div>
    </div>
    <div class=" news-layout">
      <div class="heading">
        <p class="md-text">Интересные статьи</p>
        <a href="#">
          <p style="color: var(--primary-700)">Больше</p>
          <SvgCircleArrowRight/>
        </a>
      </div>
      <div class="news-list">
        <NewsItem
            background-color="#b4dada"
            title="Неизвестные списания с карты?"
            desc="Статья · 2 мин чтения"
            background-image="/src/assets/img/news-1.png"
        />
        <NewsItem
            background-color="#f2c7b1"
            title="Чем плох возврат через банк?"
            desc="Коротко · 1 min"
            background-image="/src/assets/img/news-2.png"
        />
      </div>
    </div>
    <div class="ylw-btn-layout">
      <div class="score-box">
        <ProgressCircle :value="750"/>
        <p>Ваш кредитный рейтинг</p>
      </div>
      <div class="support-box">
        <img src="../assets/img/Chat.png" alt="chat">
        <p>Горячая линия 24/7</p>
      </div>
    </div>
    <div class="report-layout">
      <div class="report-box">
        <div class="info">
          <p class="md-text">Отчет по оплаченной услуге</p>
          <p class="xs-text">Получите полный отчет из всех МФО и МКК</p>
        </div>
      </div>
      <div class="master-box">
        <img src="../assets/img/coin-sm.png" alt="coin">
        <div class="inner-layout">
          <p>Мастер подбора кредита <span style="color: #118C4FFF">98%</span></p>
          <div class="progress-bar-outer">
            <div class="progress-bar-inner"/>
          </div>
          <div class="desc">
            <p style="width: 60%">Предложения с высокой вероятностью кредита</p>
            <div>
              <p>Начать</p>
              <SvgCircleArrowRight/>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
  <div class="tab-menu">
    <p>Главная</p>
    <p>Поддержка</p>
    <p>Подписки</p>
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
    margin-bottom: 20px;
  }

  .heading-box .heading{
    display: flex;
    justify-content: space-between;
    padding: 16px 16px 0 16px;
  }

  .btn-layout {
    display: flex;
    align-items: stretch;
    justify-content: center;
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
    padding-right: 16px;
  }

  .card-list-container::-webkit-scrollbar {
    display: none;
  }

  .card-list-container {
    -ms-overflow-style: none;
    scrollbar-width: none;
  }

  .gradient-bg {
    border-radius: 32px;
    background: linear-gradient(90deg, #E8DF0A, #2f2d02);
    padding: 3px;
    flex: 0 0 auto;
    aspect-ratio: 1;
  }

  .btn-refund{
    color: #EEEEEEFF;
    background-color: #000000FF;
    text-align: center;
    width: 100%;
    height: 100%;
    border-radius: 30px;
  }

  .btn-refund p{
    margin-top: 3px;
    max-width: 100px;
  }

  .btn-refund img{
    height: 100%;
    aspect-ratio: 1;
    max-height: 45px;
  }

  .history-block {
    background-color: #E8DF0AFF;
    border-radius: 32px;
    display: flex;
    padding: 20px;
    flex-direction: column;
    gap: 12px;
    overflow: hidden;
    flex: 1 1 auto;
    max-width: 250px;
    justify-content: center;
    height: 100%;
    background-image: url("../assets/img/Line2.svg");
    background-repeat: no-repeat;
    background-position: 190px 0;
  }

  .history-block p{
    font-family: 'Sora', sans-serif;
  }

  .bubble-layout{
    display: flex;
    overflow: hidden;
    justify-content: center;
    padding-right: 16px;
  }

  .bubble-list{
    display: flex;
    flex-direction: row;
    gap: 5px;
    width: fit-content;
  }

  .stories-list{
    display: flex;
    align-items: center;
    padding: 12px 12px 12px 0;
    overflow-x: scroll;
    -ms-overflow-style: none;
    scrollbar-width: none;
    background-color: #f4f4f4;
    border-radius: 32px;
    justify-content: space-between;
  }

  .stories-list::-webkit-scrollbar {
    display: none;
  }

  .news-layout p{
    font-family: 'Sora', sans-serif;
    font-weight: 700;
  }

  .news-layout .heading{
    display: flex;
    justify-content: unset;
    align-items: center;
    padding-left: 16px;
    margin-bottom: 8px;
    padding-top: 16px;
    gap: 20px;
  }

  .news-layout .heading a{
    display: flex;
    align-items: center;
    gap: 3px;
    padding-right: 3px;
  }

  .news-list{
    display: flex;
    overflow-x: scroll;
    padding: 0 16px 4px 0;
    -ms-overflow-style: none;
    scrollbar-width: none;
  }

  .news-list::-webkit-scrollbar {
    display: none;
  }

  .ylw-btn-layout{
    display: flex;
    gap: 16px;
    padding: 16px;
  }

  .score-box{
    display: flex;
    align-items: center;
    gap: 20px;
    width: 100%;
    padding: 16px;
    border-radius: 32px;
    background-image: url("/src/assets/img/credit-score-bg.svg");
    background-repeat: no-repeat;
    background-position: bottom right;
    background-size: cover;
  }

  .score-box p{
    font-size: 18px;
    text-transform: uppercase;
  }

  .support-box{
    width: 100%;
    display: flex;
    align-items: center;
    gap: 20px;
    padding: 16px;
    border-radius: 32px;
    border: 2px solid rgba(233, 225, 24, 0.42);
    background: linear-gradient(113.02deg, rgba(232, 223, 10, 0.2) 1.59%, rgba(249, 228, 1, 0.2) 46.31%, rgba(254, 255, 202, 0.2) 91.82%);
  }

  .support-box img{
    width: 86px;
  }

  .support-box p{
    font-size: 18px;
    text-transform: uppercase;
  }

  .report-layout{
    display: flex;
    gap: 16px;
    padding: 0 16px 16px 16px;
  }

  .report-box{
    width: 100%;
    display: flex;
    flex-direction: column-reverse;
    height: 243px;
    border-radius: 32px;
    overflow: hidden;
    background-image: url("../assets/img/report-bg.png");
    background-repeat: no-repeat;
    background-size: cover;
    background-position: center -15px;
  }

  .report-box .info{
    background-color: #e8df0a;
    padding: 12px;
    text-align: center;
  }

  .report-box .info .md-text{
    margin-bottom: 6px;
  }

  .report-box .info .xs-text{
    margin-bottom: 6px;
    font-size: 14px;
    color: var(--content-neutral);
  }

  .master-box{
    width: 100%;
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 16px;
    margin-bottom: 60px;
  }

  .master-box img{
    width: 44px;
    height: 44px;
  }

  .master-box .inner-layout{
    width: 100%;
    display: flex;
    flex-direction: column;
    gap: 8px;
  }

  .master-box .inner-layout p{
    font-size: 14px;
  }

  .master-box .progress-bar-outer{
    width: 100%;
    height: 3px;
    background-color: #70BA95FF;
    border-radius: 20px;
  }

  .master-box .progress-bar-inner{
    width: 98%;
    height: 3px;
    background-color: #014D18FF;
    border-radius: 20px;
  }

  .master-box .inner-layout .desc{
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  .master-box .inner-layout .desc div{
    display: flex;
    gap: 3px;
  }

  .master-box .inner-layout .desc div p{
    font-size: 16px;
    color: var(--primary-700);
  }

  .master-box .inner-layout .desc p{
    font-size: 12px;
    color: var(--content-neutral);
  }

  .tab-menu {
    position: fixed;
    bottom: 0;
    width: 100%;
    padding: 16px;
    background: #fff;
    display: flex;
    justify-content: space-around;
    align-items: center;
  }

  .tab-menu p{
    font-size: 12px;
  }

  @media screen and (max-width: 860px) {
    .bubble-layout{
      flex-direction: column;
      gap: 18px;
      padding-right: 0;
    }
    .stories-list{
      background-color: transparent !important;
      border-radius: 0 !important;
      padding: 0 16px 0 0;
    }
    .news-layout .heading{
      justify-content: space-between;
    }
    .ylw-btn-layout{
      flex-direction: column;
    }
    .report-layout{
      flex-direction: column;
    }
  }
</style>