<template>
  <nav class="navbar">
    <div class="user">
      <img src="@/assets/propic.jpg" alt="propic" class="user__img">
      <h2 class="user__name">金城武</h2>
    </div>
    <div class="service">
      <ul class="service__list">
        <li class="service__list__item"
        v-for="(item,index) in serviceList"
        :key="index">
          <img :src="item.icon" alt="icon">
          {{ item.title }}
          <a href="#"></a>
        </li>
      </ul>
      <div class="toggle_service_show"
      @click="handleToggleService">
        <div class="toggle_service_show__icon">
          <i :class="toggleService.icon"></i>
        </div>
          {{ toggleService.title }}
      </div>
    </div>
    <div class="shortcut">
      <h2 class="shortcut__title">你的捷徑</h2>
      <ul class="shortcut__list">
        <li class="shortcut__item"
        v-for="(item,index) in shortcut"
        :key="index">
          <img :src="item.img" alt="shortcut img" class="shortcut__item__img">
          <p class="shortcut__item__title">{{ item.title }}</p>
        </li>
      </ul>
      <div class="toggle_service_show"
      @click="handleToggleService">
        <div class="toggle_service_show__icon">
          <i :class="toggleService.icon"></i>
        </div>
          {{ toggleService.title }}
      </div>
    </div>
    <div class="copyright">
      隱私政策  · 服務條款  · 廣告  · Ad Choices   · Cookie  · Facebook © 2021
    </div>
  </nav>
</template>

<script>
import { ref } from 'vue'
export default {
  name: 'Navbar',
  setup () {
    const serviceList = [
      { icon: 'https://static.xx.fbcdn.net/rsrc.php/v3/y8/r/S0U5ECzYUSu.png', title: '朋友' },
      { icon: 'https://static.xx.fbcdn.net/rsrc.php/v3/y5/r/PrjLkDYpYbH.png', title: '社團' },
      { icon: 'https://static.xx.fbcdn.net/rsrc.php/v3/yU/r/D2y-jJ2C_hO.png', title: 'Marketplace' },
      { icon: 'https://static.xx.fbcdn.net/rsrc.php/v3/y5/r/duk32h44Y31.png', title: 'Watch' },
      { icon: 'https://static.xx.fbcdn.net/rsrc.php/v3/y8/r/he-BkogidIc.png', title: '動態回顧' },
      { icon: 'https://static.xx.fbcdn.net/rsrc.php/v3/yo/r/DO-SN-shaZL.png', title: '工作機會' },
      { icon: 'https://static.xx.fbcdn.net/rsrc.php/v3/yN/r/9s7nhm949yb.png', title: '互助情報站' },
      { icon: 'https://static.xx.fbcdn.net/rsrc.php/v3/yC/r/bo0Zt72NIra.png', title: '天氣' },
      { icon: 'https://static.xx.fbcdn.net/rsrc.php/v3/yD/r/lVijPkTeN-r.png', title: '我的珍藏' }
    ]
    const shortcut = [
      { img: 'https://picsum.photos/28/28?random=1', title: 'test' },
      { img: 'https://picsum.photos/28/28?random=2', title: '132123132' },
      { img: 'https://picsum.photos/28/28?random=3', title: 'text' },
      { img: 'https://picsum.photos/28/28?random=4', title: 'text' },
      { img: 'https://picsum.photos/28/28?random=5', title: 'text' }
    ]
    const toggleService = { icon: 'fas fa-angle-down', title: '顯示更多' }
    const handleToggleService = () => {
      toggleService.icon = 'fas fa-angle-up'
      toggleService.title = '顯示更少'
      console.log(ShowServiceCount.value)
    }
    const ShowServiceCount = ref(5)
    return {
      serviceList, toggleService, handleToggleService, ShowServiceCount, shortcut
    }
  }
}
</script>

<style lang="scss" scoped>
@import '@/style/variable.scss';
.navbar::-webkit-scrollbar {
  width: .08rem;
}

.navbar::-webkit-scrollbar-track {
  background: $background;
}

::-webkit-scrollbar-thumb {
  background: $hover_color;
  border-radius: .5rem;
}
.navbar {
  width: 22%;
  max-width: 3.6rem;
  min-width: 2.8rem;
  height: 100%;
  overflow-y: auto;
  padding: 0.16rem .08rem;
  .user {
    display: flex;
    align-items: center;
    height: 0.44rem;
    padding: 0 0.12rem;
    border-radius: 0.1rem;
    cursor: pointer;
    &:hover {
      background-color: $hover_color;
    }
    &__img {
        width: 0.28rem;
        margin-right: 0.08rem;
        border-radius: .5rem;
      }
      &__name {
        font-size: 0.15rem;
        padding: 0;
      }
  }
  .service {
    border-bottom: .01rem solid rgba(255, 255, 255, .2);
    padding-bottom: 0.08rem;
    &__list {
      &__item {
        position: relative;
        height: 0.44rem;
        font-weight: 600;
        line-height: 0.44rem;
        padding: 0 0.08rem;
        border-radius: .1rem;
        &:hover {
          background-color: $hover_color;
        }
        img {
          width: 0.28rem;
          display: inline-block;
          vertical-align: middle;
          margin-right: 0.08rem;
        }
        a {
          position: absolute;
          top: 0;
          right: 0;
          bottom: 0;
          left: 0;
        }
      }
    }
  }
  .toggle_service_show {
    display: flex;
    align-items: center;
    padding: 0 0.08rem;
    height: 0.44rem;
    border-radius: .1rem;
    cursor: pointer;
    &:hover {
      background-color: $hover_color;
    }
    &__icon {
      width: 0.28rem;
      height: 0.28rem;
      line-height: 0.3rem;
      text-align: center;
      background-color: $tool_bg;
      border-radius: 50%;
      margin-right: 0.12rem;
    }
  }
  .shortcut {
    padding: 0.16rem 0;
    &__title {
      margin: 0;
      padding: 0 0.08rem;
      font-size: 0.17rem;
      color: $secondary_text;
    }
    &__item {
      display: flex;
      align-items: center;
      height: 0.44rem;
      padding: 0 0.08rem;
      border-radius: .1rem;
      cursor: pointer;
      &:hover {
        background-color: $hover_color;
      }
      img {
        margin-right: 0.12rem;
        border-radius: .08rem;
      }
    }
  }
  .copyright {
    font-size: 0.13rem;
    line-height: 1.5;
    color: $secondary_text;
    padding: 0 0.08rem;
  }
}
</style>
