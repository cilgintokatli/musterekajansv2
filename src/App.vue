<template>
  <div id="app">
    <div class="wrapper">
      <header>logo</header>
      <div class="slides">
        <div v-for="(item,index) in slides"
             :key="index"
             :class="[selected === item.id ? 'active' : '', 'slide-'+item.id]">
          <figure class="photo">
            <img :src="item.src" alt>
          </figure>
          <div class="description">{{ item.desc }}</div>
        </div>
      </div>
      <nav>
        <h2 v-for="(item, index) in slides" :key="index">
          <span @click="selected = item.id" :class="{clicked:selected === item.id}">
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
          title: 'new york',
          id: 1,
          src: 'https://images.unsplash.com/photo-1518235506717-e1ed3306a89b?ixlib=rb-1.2.1&auto=format&fit=crop&w=1500&q=80',
          desc: 'deneme 1'
        },
        {
          title: 'paris',
          id: 2,
          src: 'https://images.unsplash.com/photo-1502602898657-3e91760cbb34?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1504&q=80',
          desc: 'deneme 2'
        },
        {
          title: 'london',
          id: 3,
          src: 'https://images.unsplash.com/photo-1474606030380-107829a22fc6?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1500&q=80',
          desc: 'deneme 3',
        },
        {
          title: 'istanbul',
          id: 4,
          src: 'https://images.unsplash.com/photo-1516710505574-0245114a1093?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1500&q=80',
          desc: 'deneme 4'
        },
        {
          title: 'tokyo',
          id: 5,
          src: 'https://images.unsplash.com/photo-1494587416117-f102a2ac0a8d?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1500&q=80',
          desc: 'deneme 5'
        }
      ],
      selected: 1,
    }
  }
};
</script>

<style lang="scss">
@import "../src/assets/scss/main.scss";
</style>
