<script setup>
import { Swiper, SwiperSlide } from 'swiper/vue'
import 'swiper/css'
import 'swiper/css/pagination'
import 'swiper/css/navigation'
import { Pagination, Navigation } from 'swiper/modules'
</script>

<template>
  <div class="carousel-wrapper">
    <swiper
        :modules="[Pagination, Navigation]"
        :slides-per-view="3"
        :space-between="20"
        :loop="false"
        navigation
        pagination
        class="custom-swiper"
    >
      <swiper-slide v-for="n in 5" :key="n">
        <div class="card">Карточка {{ n }}</div>
      </swiper-slide>
    </swiper>

    <!-- Навигация вынесена за пределы контейнера -->
    <div class="swiper-button-prev"></div>
    <div class="swiper-button-next"></div>
  </div>
</template>

<style scoped>
/* Внешний контейнер */
.carousel-wrapper {
  position: relative;
  width: 1224px;
  margin: 0 auto;
  padding: 0 80px; /* Добавляем отступы, чтобы стрелки не перекрывали контент */
}

/* Внутренний контейнер */
.custom-swiper {
  width: 100%;
}

/* Карточки */
.card {
  display: flex;
  align-items: center;
  justify-content: center;
  height: 242px;
  width: 352px;
  background: #B2B0C0;
  border-radius: 16px;
}

/* Стили для стрелок (навигaция) */
:deep(.swiper-button-next),
:deep(.swiper-button-prev) {
  color: orange;
  font-weight: bold;
  width: 50px;
  height: 50px;
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
}

/* Смещаем стрелки за контейнер */
:deep(.swiper-button-prev) {
  left: -30px; /* Вынесена за контейнер */
}

:deep(.swiper-button-next) {
  right: -30px; /* Вынесена за контейнер */
}

/* Увеличенный размер стрелок */
:deep(.swiper-button-next:after),
:deep(.swiper-button-prev:after) {
  font-size: 32px;
}

/* Пагинация (точки) */
:deep(.swiper-pagination) {
  position: absolute;
  bottom: -50px; /* Сместили ниже контейнера */
  left: 50%;
  transform: translateX(-50%);
}

/* Точки */
:deep(.swiper-pagination-bullet) {
  background: orange;
  width: 10px;
  height: 10px;
  border-radius: 12px;
  opacity: 0.4;
}

:deep(.swiper-pagination-bullet-active) {
  background: orange;
  width: 11px;
  height: 11px;
  opacity: 1;
}
</style>
