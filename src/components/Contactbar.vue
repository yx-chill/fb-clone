<template>
  <section class="contactbar">
    <div class="sponsor">
      <h2 class="sponsor__title">贊助</h2>
      <ul class="sponsor__list">
        <li class="sponsor__list__item"></li>
      </ul>
    </div>
    <div class="directory">
      <div class="directory__header">
        <h2 class="directory__title">聯絡人</h2>
        <ui class="directory__option">
          <li class="directory__option__item">
            <i class="fas fa-video"></i>
          </li>
          <li class="directory__option__item">
            <i class="fas fa-search"></i>
          </li>
          <li class="directory__option__item">
            <i class="fas fa-ellipsis-h"></i>
          </li>
        </ui>
      </div>
      <ul class="directory__list">
        <li class="directory__item"
        v-for="i in fakeImgNum"
        :key="i">
          <img :src="`https://picsum.photos/28/28?random=${i}`" alt="user photo"
          class="directory__item__img">
          <span></span>
          <h3 class="directory__item__name">test</h3>
        </li>
      </ul>
    </div>
    <div class="directory__group">
      <h2 class="directory__group__title">群組對話</h2>
      <div class="directory__creategroup">
        <div class="directory__creategroup__icon">
          <i class="fas fa-plus"></i>
        </div>
        <h3>建立新群組</h3>
      </div>
    </div>
    <div class="contactbar__newmessage">
      <i class="fas fa-edit"></i>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Contactbar',
  setup () {
    const fakeImgNum = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
    return { fakeImgNum }
  }
}
</script>

<style lang="scss" scoped>
@import '@/style/variable.scss';
.contactbar::-webkit-scrollbar {
  width: .08rem;
}

.contactbar::-webkit-scrollbar-track {
  background: $background;
}

::-webkit-scrollbar-thumb {
  background: $hover_color;
  border-radius: .5rem;
}
.contactbar {
  width: 25%;
  max-width: 3.6rem;
  min-width: 2.8rem;
  height: 100%;
  padding: 0.16rem 0.08rem;
  overflow-y: auto;
  .sponsor {
    padding: 0.08rem;
    &__title {
      font-size: 0.17rem;
      color: $secondary_text;
      margin: 0;
    }
    &__list {
      padding: 0.08rem 0;
      border-bottom: .01rem solid rgba(255, 255, 255, .2);
    }
  }
  .directory {
    &__header {
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 0 0.08rem;
    }
    &__title {
      font-size: 0.17rem;
      color: $secondary_text;
      margin: 0;
    }
    &__option {
      display: flex;
      align-items: center;
      list-style: none;
      &__item {
        width: 0.32rem;
        height: 0.32rem;
        text-align: center;
        border-radius: .5rem;
        margin-left: 0.12rem;
        cursor: pointer;
        &:hover {
          background-color: $hover_color;
        }
        i {
          font-size: 0.16rem;
          line-height: 0.32rem;
          color: $secondary_text;
        }
      }
    }
    &__list {
      padding-bottom: 0.08rem;
    }
    &__item {
      display: flex;
      align-items: center;
      height: 0.44rem;
      padding: 0 0.08rem;
      border-radius: .1rem;
      position: relative;
      cursor: pointer;
      &:hover {
        background-color: $hover_color;
      }
      &__img {
        border-radius: .5rem;
        margin-right: 0.12rem;
      }
      span {
        position: absolute;
        bottom: 0.08rem;
        left: .28rem;
        width: 0.1rem;
        height: 0.1rem;
        background-color: $online;
        border-radius: .5rem;
        border: .02rem solid $background;
      }
    }
    &__group {
      padding: 0 0.08rem;
      &__title {
        border-top: .01rem solid rgba(255, 255, 255, .2);
        font-size: 0.17rem;
        color: $secondary_text;
        margin: 0;
        padding-top: 0.16rem;
        margin-bottom: 0.08rem;
      }
    }
    &__creategroup {
      height: 0.44rem;
      display: flex;
      align-items: center;
      text-align: center;
      border-radius: .1rem;
      padding-left: 0.08rem;
      margin-left: -.08rem;
      cursor: pointer;
      &:hover {
        background-color: $hover_color;
      }
      &__icon {
        width: 0.28rem;
        height: 0.28rem;
        border-radius: .5rem;
        background-color: $tool_bg;
        margin-right: 0.08rem;
        i {
          line-height: 0.28rem;
        }
      }
      h3 {
        margin: 0;
        font-size: 0.15rem;
      }
    }
  }
  &__newmessage {
    width: 0.48rem;
    height: 0.48rem;
    text-align: center;
    border-radius: .5rem;
    background-color: $tool_bg;
    position: absolute;
    right: 0.2rem;
    bottom: 0.2rem;
    i {
      font-size: 0.2rem;
      line-height: 0.45rem;
    }
  }
}
</style>
