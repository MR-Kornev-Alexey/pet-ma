<script setup>
import { Swiper, SwiperSlide } from 'swiper/vue'
import 'swiper/css'
import 'swiper/css/pagination'
import 'swiper/css/navigation'
import { Pagination, Navigation } from 'swiper/modules'
</script>

<template>
  <swiper
      :modules="[Pagination, Navigation]"
      :slides-per-view="3"
      :space-between="20"
      :loop="false"
      navigation
      pagination
  >
    <swiper-slide v-for="n in 6" :key="n">
      <div class="card">Карточка {{ n }}</div>
    </swiper-slide>
  </swiper>
</template>

<style scoped>
.card {
  display: flex;
  align-items: center;
  justify-content: center;
  height: 200px;
  width: 200px;
  background: #ddd;
  border-radius: 10px;
}
</style>