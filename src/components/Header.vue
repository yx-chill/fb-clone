<template>
  <header class="header">
    <div class="search__block">
      <div class="logo">
        <img
          src="https://1000logos.net/wp-content/uploads/2016/11/FacebookPNG.png"
          alt="facebook icon"
        />
        <a href="/"></a>
      </div>
      <div class="search">
        <i class="fas fa-search"></i>
        <input type="search" placeholder="搜尋 Facebook" />
      </div>
    </div>
    <div class="toggle__block">
      <ul class="toggle__list">
        <li class="toggle__list__item"
        v-for="item in toggleIcon"
        :key="item.class"
        :class="{ 'active': item.active }">
          <i :class="item.class"></i>
          <span v-if="item.notify !== '0'">{{ item.notify }}</span>
        </li>
      </ul>
    </div>
    <div class="user__block">
      <div class="user">
        <img src="@/assets/propic.jpg" alt="propic" class="user__img">
        <h2 class="user__name">金城武</h2>
      </div>
      <ul class="func">
        <li class="func__item"
        v-for="item in funcIcon"
        :key="item.class">
          <i :class="item.class"></i>
        </li>
      </ul>
    </div>
  </header>
</template>

<script>
export default {
  name: 'Header',
  setup () {
    const toggleIcon = [
      { class: 'fas fa-home', notify: '0', active: false },
      { class: 'fas fa-video', notify: '99+', active: false },
      { class: 'fas fa-store', notify: '0', active: false },
      { class: 'fas fa-users', notify: '0', active: false },
      { class: 'fas fa-gamepad', notify: '1', active: false }
    ]
    const funcIcon = [
      { class: 'fas fa-th' },
      { class: 'fab fa-facebook-messenger' },
      { class: 'fas fa-bell' },
      { class: 'fas fa-caret-down' }
    ]
    return { toggleIcon, funcIcon }
  }
}
</script>

<style lang="scss" scoped>
@import '@/style/variable.scss';
.header {
  padding: 0 0.16rem;
  border-bottom: 1px solid rgba(255, 255, 255, 0.1);
  display: flex;
  justify-content: space-between;
  align-items: center;
  height: 0.56rem;
  background-color: $header_bg;
  position: sticky;
  z-index: 5;
  .search__block {
    display: flex;
    align-items: center;
  }
  .logo {
    position: relative;
    img {
      width: 0.4rem;
      border-radius: 50%;
      margin-right: 0.1rem;
    }
    a {
      position: absolute;
      top: 0;
      right: 0;
      bottom: 0;
      left: 0;
    }
  }
  .search {
    width: 2.4rem;
    height: 0.4rem;
    position: relative;
    input {
      width: 100%;
      height: 100%;
      background: $tool_bg;
      border: none;
      outline: none;
      padding: 0.08rem 0.16rem 0.08rem 0.36rem;
      border-radius: 50px;
      font-size: 0.15rem;
      caret-color: $primary_text;
    }
    i {
      position: absolute;
      top: 0.12rem;
      left: 0.1rem;
      font-size: 0.16rem;
    }
  }
  .toggle__block {
    height: 0.56rem;
    width: 6rem;
    .toggle__list {
      display: flex;
      justify-content: space-between;
      text-align: center;
      padding: 0;
      &__item {
        width: 20%;
        height: 100%;
        margin: 0 0.04rem;
        border-radius: .10rem;
        cursor: pointer;
        position: relative;
        &::before {
          content: '';
          // width: 100%;
          height: 0.02rem;
          background-color: $icon_color;
          border-radius: 50%;
          display: block;
          position: absolute;
          bottom: 0;
        }
        &:hover {
          background: $tool_bg;
        }
      }
      i {
        font-size: 0.26rem;
        line-height: .56rem;
      }
      span {
        position: absolute;
        top: 10%;
        right: 25%;
        font-size: 0.13rem;
        line-height: 0.2rem;
        background-color: $notify;
        padding: 0 0.05rem;
        border-radius: .5rem;
      }
    }
  }

  .user__block {
    display: flex;
    align-items: center;
    .user {
      display: flex;
      align-items: center;
      height: 0.36rem;
      padding: 0 0.12rem;
      border-radius: 0.5rem;
      cursor: pointer;
      &:hover {
        background-color: $tool_bg;
      }
      &__img {
        width: 0.28rem;
        margin-right: 0.06rem;
        border-radius: .5rem;
      }
      &__name {
        font-size: 0.15rem;
        padding: 0;
      }
    }
    .func {
      display: flex;
      &__item {
        width: 0.4rem;
        height: 0.4rem;
        text-align: center;
        border-radius: 50%;
        background-color: $tool_bg;
        margin: 0 0.04rem;
        cursor: pointer;
        &:hover {
          background: lighten($tool_bg, 10%);
        }
        i {
          font-size: 0.2rem;
          line-height: 2;
        }
      }
    }
  }
}
.active {
  &::before {
    width: 100%;
  }
  i {
    color: $icon_color;
  }
}
</style>
