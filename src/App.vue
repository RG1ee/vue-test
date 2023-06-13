<template>
  <div :class="{ 'bg-gray-700': isDarkMode }">
    <header class="sticky top-0 z-20 flex justify-between p-3">
      <a href="#">
        <img src="./assets/img/cat.png" alt="logo" class="h-9" />
      </a>
      <button @click="toggleTheme">
        <img :src="imageSource" alt="Тема" class="h-9" />
      </button>
    </header>
    <div class="flex h-screen flex-col items-center justify-center">
      <h2 :class="textClass">{{ text }}</h2>
      <div class="flex space-x-4">
        <a href="https://instagram.com/whykittzy/">
          <img
            src="./assets/img/instagram.png"
            alt="instagram"
            class="h-8 w-8 md:h-12 md:w-12 lg:h-16 lg:w-16"
          />
        </a>
        <a href="https://t.me/whykittzy">
          <img
            src="./assets/img/telegram.png"
            alt="telegram"
            class="h-8 w-8 md:h-12 md:w-12 lg:h-16 lg:w-16"
          />
        </a>
        <a href="mailto:sayhellokittzy@gmail.com">
          <img
            src="./assets/img/gmail.png"
            alt="gmail"
            class="h-8 w-8 md:h-12 md:w-12 lg:h-16 lg:w-16"
          />
        </a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isDarkMode: false,
      imageSource: 'src/assets/img/night.png',
      text: 'Roman Lee'
    }
  },
  computed: {
    textClass() {
      return this.isDarkMode
        ? 'text-3xl font-bold text-center mb-4 text-white'
        : 'text-3xl font-bold text-center mb-4 text-black'
    }
  },
  methods: {
    toggleTheme() {
      this.isDarkMode = !this.isDarkMode
      document.documentElement.classList.toggle('dark')

      // Изменяем путь к изображению в зависимости от темы
      if (this.isDarkMode) {
        this.imageSource = 'src/assets/img/moon.png'
        this.text = 'Roman Lee'
      } else {
        this.imageSource = 'src/assets/img/night.png'
        this.text = 'Roman Lee'
      }
    }
  }
}
</script>
