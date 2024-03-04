<template>
    <div class="expansion-panel">
      <div v-for="(item, index) in items" :key="index" class="panel">
        <div class="panel-header" @click="togglePanel(index)">
          {{ item.title }}
          <span :class="{ 'rotate-arrow': item.open }">&#9660;</span>
        </div>
        <transition name="fade-in">
          <div v-if="item.open" class="panel-content">
            {{ item.content }}
          </div>
        </transition>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        items: [
          { title: 'Embrace Cultural Heritage', content: 'Celebrate and deepen your understanding of Latino culture.', open: false },
          { title: 'Develop leadership skills', content: 'Take on roles that build confidence and leadership abilities', open: false },
          { title: 'Community service', content: 'Give back through meaningful service projects and make a positive impact.', open: false },
          { title: 'Make lifelong friends', content: 'Join a welcoming community where strong friendships are formed.', open: false },
        ],
      };
    },
    methods: {
      togglePanel(index) {
        this.items[index].open = !this.items[index].open;
      },
    },
  };
  </script>
  
  <style scoped>
  .expansion-panel {
    width: 100%;
  }
  
  .panel {
    border: 1px solid #ddd;
    margin-bottom: 5px;
  }
  
  .panel-header {
    padding: 10px;
    background-color: #f2f2f2;
    cursor: pointer;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  
  .rotate-arrow {
    transition: transform 0.3s ease-in-out;
  }
  
  .panel-content {
    padding: 10px;
    border-top: 1px solid #ddd;
    overflow: hidden;
  }
  
  .fade-in-enter-active {
    transition: opacity 0.5s ease-in-out;
  }
  
  .fade-in-enter {
    opacity: 0;
  }
  
  .fade-in-leave-to {
    opacity: 0;
  }
  </style>
  