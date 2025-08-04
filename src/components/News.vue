<script setup>
defineProps({
  img: String,
  date: String,
  likes: Number,
  title: String,
  isFirst: Boolean,
  isLast: Boolean,
})
</script>

<template>
  <div
    class="news-card"
    :style="{
      border: '1px solid #999999',
      borderTopLeftRadius: isFirst ? '20px' : '0px',
      borderTopRightRadius: isFirst ? '20px' : '0px',
      borderBottomLeftRadius: isLast ? '20px' : '0px',
      borderBottomRightRadius: isLast ? '20px' : '0px',
    }"
  >
    <img :src="img" alt="img" class="news-img" />
    <div class="news-content">
      <div class="flex space-between">
        <p class="date">{{ date }}</p>
        <div class="flex likes">
          <img src="../assets/img/Heart.svg" alt="heart" />
          <p class="like-count">{{ likes }}</p>
        </div>
      </div>
      <p class="title">{{ title }}</p>
    </div>
  </div>
</template>
<style scoped>
.flex {
  display: flex;
}

.space-between {
  justify-content: space-between;
}

.news-card {
  padding: 20px;
  display: flex;
  gap: 30px;
  align-items: flex-start;
}

.news-img {
  width: 120px;
  height: auto;
  object-fit: cover;
}

.news-content {
  width: 100%;
}

.date {
  color: #999999;
  font-size: 14px;
}

.likes {
  gap: 5px;
}

.like-count {
  color: #FFB2B2;
}

.title {
  font-size: 20px;
  line-height: 30px;
  margin-top: 10px;
}

/* Responsive for mobile */
@media (max-width: 768px) {
  .news-card {
    flex-direction: column;
    gap: 15px;
    padding: 15px;
  }

  .news-img {
    width: 100%;
    height: auto;
  }

  .title {
    font-size: 18px;
    line-height: 26px;
  }

  .date {
    font-size: 12px;
  }

  .like-count {
    font-size: 14px;
  }
}
</style>
