<template>
  <div class="news__item">
    <h3>{{ title }}</h3>
    <button class="btn btn-primary" @click="toggleOpen">Открыть</button>
    <p v-if="isOpen">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Aliquam assumenda aut dignissimos, distinctio officia qui soluta unde? Asperiores consequatur iure maiores necessitatibus reprehenderit! Expedita, magni, ratione. Minus perferendis soluta voluptatem.</p>
  </div>
</template>

<script>
export default {
  // props: ['title'],
    props: {
      title: String,
      id: Number,
      isOpen: Boolean,
    },
  data() {
    return {
      // isOpen: false,
    }
  },
  watch: {
      isOpen(newValue) {
        this.localIsOpen = newValue
      }
  },
  methods: {
    toggleOpen() {
      this.localIsOpen = !this.localIsOpen
      this.$emit("update:isOpen", this.localIsOpen)
    }
  },
}
</script>