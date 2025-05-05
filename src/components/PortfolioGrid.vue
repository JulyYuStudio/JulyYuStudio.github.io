<template>
    <div class="portfolio-grid">
        <div class="portfolio-item" v-for="(item, idx) in projects" :key="idx" :data-title="item.name" @click="item.url && openLink(item.url)">
          <img :src="item.img" alt="portfolio work" />
        </div>
    </div>
  </template>


<script setup>
const openLink = (url) => {
  window.open(url, '_blank');
};

const projects = [
  {
    name: 'CloudPhone',
    img: 'https://dummyimage.com/400x300/ededed/333333&text=Work+1',
    url: 'https://studio.julyyu.cn/CloudPhone/'
  },
  {
    name: '余小余周刊',
    img: 'https://dummyimage.com/400x300/ededed/333333&text=Work+2',
    url: 'https://studio.julyyu.cn/Web_Weekly/'
  },
  {
    name: '桌面时钟',
    img: 'https://dummyimage.com/400x300/ededed/333333&text=Work+3',
    url: 'https://play.google.com/store/apps/details?id=com.july.yu.clock'
  },

];
</script>


<style scoped>

.portfolio-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 64px 60px;
  width: 100%;
  /* padding: 12px 0 48px 0; */
}
.portfolio-item {
  background: #fff;
  border-radius: 8px;
  box-shadow: 0 2px 12px 0 rgba(0,0,0,0.04);
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 0;
  overflow: hidden;
  aspect-ratio: 4/3;
  position: relative;
  transition: all 0.3s ease;
}

.portfolio-item:hover {
  box-shadow: 0 8px 24px 0 rgba(0,0,0,0.12);
}

.portfolio-item:hover::after {
  content: attr(data-title);
  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
  background: rgba(0,0,0,0.7);
  color: white;
  padding: 8px;
  text-align: center;
  font-size: 0.9rem;
}
.portfolio-item img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  display: block;
}
@media (max-width: 900px) {
  .portfolio-grid {
    grid-template-columns: repeat(2, 1fr);
    gap: 40px 32px;
  }
}
@media (max-width: 600px) {
  .portfolio-title {
    font-size: 1.3rem;
  }
  .portfolio-subtitle {
    font-size: 0.95rem;
  }
  .portfolio-grid {
    grid-template-columns: 1fr;
    gap: 30px 0;
    max-width: 98vw;
  }
}
</style>