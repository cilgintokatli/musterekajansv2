<template>
  <div id="app">
    <div class="wrapper">
      <header>
        <h1 class="logo">müşterek ajans</h1>
      </header>
      <div class="slides">
        <div
          v-for="(item, index) in slides"
          :key="index"
          :class="[selected === item.id ? 'active' : '', 'slide-' + item.id]"
        >
          <figure class="photo">
            <img :src="item.src" alt />
          </figure>
          <div class="description">{{ item.desc }}</div>
        </div>
      </div>
      <nav>
        <h2 v-for="(item, index) in slides" :key="index">
          <span
            @click="selected = item.id"
            :class="{ clicked: selected === item.id }"
          >
            {{ item.title }}
          </span>
        </h2>
      </nav>
    </div>
  </div>
</template>

<script>
export default {
  name: "app",
  data() {
    return {
      slides: [
        {
          title: "video kurgu",
          id: 1,
          src:
            "https://images.unsplash.com/photo-1518235506717-e1ed3306a89b?ixlib=rb-1.2.1&auto=format&fit=crop&w=1500&q=80",
          desc: "video kurgu"
        },
        {
          title: "web tasarım",
          id: 2,
          src:
            "https://images.unsplash.com/photo-1502602898657-3e91760cbb34?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1504&q=80",
          desc: "web tasarım"
        },
        {
          title: "grafik tasarım",
          id: 3,
          src:
            "https://images.unsplash.com/photo-1474606030380-107829a22fc6?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1500&q=80",
          desc: "grafik tasarım"
        },
        {
          title: "sosyal medya",
          id: 4,
          src:
            "https://images.unsplash.com/photo-1516710505574-0245114a1093?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1500&q=80",
          desc: "sosyal medya"
        },
        {
          title: "baskı",
          id: 5,
          src:
            "https://images.unsplash.com/photo-1494587416117-f102a2ac0a8d?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1500&q=80",
          desc: "baskı"
        },
        {
          title: "iletişim",
          id: 6,
          src:
            "https://images.unsplash.com/photo-1494587416117-f102a2ac0a8d?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1500&q=80",
          desc: "iletişim sayfası"
        }
      ],
      selected: 1
    };
  }
};
</script>

<style lang="scss">
@import "../src/assets/scss/main.scss";
</style>
