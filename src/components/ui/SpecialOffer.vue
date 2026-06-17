<script setup lang="ts">
import { ref } from 'vue';

interface MaterialItem {
  id: string;
  title: string;
  image: string;
}

interface Props {
  promoText?: string;
}

withDefaults(defineProps<Props>(), {
  promoText: 'Акции'
});

const materials = ref<MaterialItem[]>([
  { id: '1', title: 'Кулирная гладь', image: 'kulglad.svg' },
  { id: '2', title: 'Футер', image: 'footer.svg' },
  { id: '3', title: 'Кашкорсе, риабана', image: 'kashkorse.svg' },
  { id: '4', title: 'Пике', image: 'pike.svg' },
  { id: '5', title: 'Интерлок', image: 'interlock.svg' },
  { id: '6', title: 'Капитоний', image: 'kapitoniy.svg' },
  { id: '7', title: 'Селаник', image: 'selanick.svg' },
  { id: '8', title: 'Велюр', image: 'velour.svg' },
  { id: '9', title: 'Вискоза', image: 'viskoza.svg' },
]);

const getImageUrl = (name: string) => {
  return new URL(`../../assets/icons/${name}`, import.meta.url).href;
};
</script>

<template>
  <div class="info-strip">
    <div class="strip-container">
      <div class="promo-section">
        <span class="promo-text">{{ promoText }}</span>
      </div>

      <div class="materials-list">
        <div 
          v-for="item in materials" 
          :key="item.id" 
          class="material-item"
        >
          <div class="material-circle">
            <img :src="getImageUrl(item.image)" :alt="item.title" class="material-img" />
          </div>
          <span class="material-title">{{ item.title }}</span>
        </div>
      </div>

    </div>
  </div>
</template>

<style scoped>
.info-strip {
  width: 100%;
  background-color: #19242F;
  padding: 0px 100px;
  box-sizing: border-box;
}

/* ИСПРАВЛЕНО: Главный контейнер теперь принудительно включает скроллбар при переполнении */
.strip-container {
  max-width: 1440px;
  margin: 0 auto;
  display: flex;
  align-items: center;
  gap: 30px;
  width: 100%;
  overflow-x: auto; /* Включает прокрутку */
  scrollbar-width: thin; /* Гарантирует появление тонкого ползунка в Firefox */
  scrollbar-color: #ffd678 #243241; /* Цвет ползунка и дорожки в Firefox */
  -webkit-overflow-scrolling: touch;
}

/* ИСПРАВЛЕНО: Стилизация ползунка прокрутки для Chrome, Safari, Edge, чтобы он гарантированно отображался */
.strip-container::-webkit-scrollbar {
  height: 6px; /* Высота горизонтального ползунка под списком */
  display: block !important; /* Отменяем прошлое скрытие */
}

.strip-container::-webkit-scrollbar-track {
  background: #243241; /* Цвет дорожки скролла */
  border-radius: 3px;
}

.strip-container::-webkit-scrollbar-thumb {
  background: #ffd678; /* Цвет самого ползунка (под цвет Акций) */
  border-radius: 3px;
}

.promo-section {
  background-color: #ffd678;
  padding: 12px 35px 12px 20px;
  clip-path: polygon(0% 0%, 100% 0%, 75% 100%, 0% 100%);
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  flex-shrink: 0; /* Запрещает параллелограмму сжиматься, выталкивая скролл */
}

.promo-text {
  font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
  font-size: 15px;
  font-weight: 700;
  color: #19242F;
}

/* ИСПРАВЛЕНО: Убран overflow-x, чтобы не ломать контейнер-родитель */
.materials-list {
  display: flex;
  align-items: center;
  gap: 24px;
  flex-grow: 1;
}

.material-item {
  display: flex;
  align-items: center;
  gap: 8px;
  cursor: pointer;
  flex-shrink: 0; /* Запрещает карточкам тканей деформироваться */
}

.material-circle {
  width: 32px;
  height: 32px;
  border-radius: 50%;
  overflow: hidden;
  background-color: #e2e8f0;
  border: 1px solid #cbd5e1;
  display: flex;
  align-items: center;
  justify-content: center;
}

.material-img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.material-title {
  font-family: sans-serif;
  font-size: 13px;
  color: #e2e8f0;
  font-weight: 500;
  white-space: nowrap;
}

@media (max-width: 1200px) {
  .info-strip {
    padding: 0px 40px;
  }
}

@media (max-width: 768px) {
  .info-strip {
    padding: 0px 20px;
  }
}
</style>
