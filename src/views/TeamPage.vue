<template>
  <div class="team-page">
    <h1>我们的团队</h1>
    <div class="team-members">
      <div v-for="member in teamMembers" :key="member.id" class="member-card">
        <img :src="member.avatar" :alt="member.name" />
        <h3>{{ member.name }}</h3>
        <p>{{ member.position }}</p>
        <p>{{ member.bio }}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'TeamPage',
  data() {
    return {
      teamMembers: [
        {
          id: 1,
          name: '张三',
          position: 'CEO',
          bio: '公司创始人，10年行业经验',
          avatar: 'https://via.placeholder.com/150'
        },
        {
          id: 2,
          name: '李四',
          position: 'CTO',
          bio: '技术负责人，全栈开发专家',
          avatar: 'https://via.placeholder.com/150'
        }
      ]
    }
  }
}
</script>

<style scoped>
.team-page {
  max-width: 1200px;
  margin: 0 auto;
  padding: 2rem;
}
.team-members {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  gap: 2rem;
}
.member-card {
  background: #fff;
  border-radius: 8px;
  padding: 1.5rem;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
}
.member-card img {
  width: 100%;
  height: auto;
  border-radius: 4px;
}
</style>