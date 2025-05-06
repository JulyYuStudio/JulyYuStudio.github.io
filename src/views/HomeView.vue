<template>
  <div class="portfolio-container">
    <h1 class="portfolio-title">JulyYu Studio</h1>
    <div class="portfolio-subtitle">All Projects</div>
    <Portfolios/>
  </div>
</template>

<script setup>
import Portfolios from '../components/Portfolios.vue';
</script>

<style scoped>
.portfolio-container {
  min-height: 100vh;
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
}
.portfolio-title {
  font-size: 2.2rem;
  letter-spacing: 0.1em;
  font-weight: bold;
  margin-bottom: 10px;
  color: #000;
  text-align: center;
}
.portfolio-subtitle {
  font-size: 1.1rem;
  letter-spacing: 0.1em;
  color: #333;
  margin-bottom: 20px;
  text-align: center;
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