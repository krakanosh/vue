<template>
  <div class="container p-2">
    <div class="card p-2">
      <h2>Актуальные новости {{ now }}</h2>
    </div>
    <app-news
        v-for="item in news"
        :key="item.id"
        :title="item.title"
        :id="item.id"
        v-model:is-open="item.isOpen">
    </app-news>
  </div>
</template>

<script>
import AppNews from "@/AppNews.vue";

export default {
  data() {
    return {
      now: new Date().toLocaleDateString(),
      news: [
        {
          title: 'Дональд Трамп победил на выборах в США',
          id: 1,
          isOpen: false,
        },
        {
          title: 'Vue 3 успешно работает',
          id: 2,
          isOpen: false,
        },
      ],
    }
  },
  components: {
    'app-news': AppNews
  }
}
</script>
