<template>
    <div class="portfolio-list">
        <div class="portfolio-item" v-for="(item, idx) in projects" :key="idx" @click="item.url && openLink(item.url)">
          <img :src="item.img" alt="item.name" />
          <div class="portfolio-info">
            <div class="portfolio-name">{{ item.name }}</div>
            <div class="portfolio-des">{{ item.des }}</div>
          </div>
        </div>
    </div>
  </template>


<script setup>
const openLink = (url) => {
  window.open(url, '_blank');
};

import webphone from '../assets/webphone.png';
import weekly from '../assets/weekly.png';
import appclock from '../assets/appclock.png';

const projects = [
  {
    name: 'CloudPhone',
    img: webphone,
    url: 'https://studio.julyyu.cn/CloudPhone/',
    des: "基于NuxtJS实现的仿真手机桌面。"
  },
  {
    name: '余小余周刊',
    img: weekly,
    url: 'https://studio.julyyu.cn/Web_Weekly/',
    des: "基于Vue3并采用Trae实现的程序员技术周刊，不出意外会每周更新。"
  },
  {
    name: '桌面时钟',
    img: appclock,
    url: 'https://play.google.com/store/apps/details?id=com.july.yu.clock',
    des: "一个简约的Android时钟应用，使用Flutter技术栈实现完成。"
  },

];
</script>


<style scoped>

.portfolio-list {
  display: flex;
  flex-direction: column;
  gap: 24px;
  width: 100%;
  padding-bottom: 50px;
}
.portfolio-item {
  background: #fff;
  border-radius: 8px;
  box-shadow: 0 2px 12px 0 rgba(0,0,0,0.04);
  display: flex;
  padding: 16px;
  overflow: hidden;
  position: relative;
  transition: all 0.3s cubic-bezier(0.25, 0.8, 0.25, 1);
  cursor: pointer;
  align-items: flex-start;
}

.portfolio-item:hover {
  box-shadow: 0 12px 32px 0 rgba(0,0,0,0.16);
  transform: translateY(-2px);
}

.portfolio-item img {
  width: 200px;
  height: auto;
  object-fit: contain;
  display: block;
  margin-right: 20px;
  border-radius: 8px;
  border: 0.5px solid #00000022;
}

.portfolio-info {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  height: auto;
}
.portfolio-name {
  color: #333;
  font-size: 1.3rem;
  font-weight: bold;
  margin-bottom: 4px;
  text-align: left;
}
.portfolio-des {
  font-size: 0.9rem;
  color: #666;
}
@media (max-width: 600px) {
  .portfolio-item {
    flex-direction: column;
  }
  .portfolio-item img {
    width: 100%;
    height: auto;
    margin-right: 0;
    margin-bottom: 12px;
  }
}
</style>