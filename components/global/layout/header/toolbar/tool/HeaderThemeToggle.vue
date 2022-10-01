<template>
  <div class="px-[20px] cursor-pointer" @click="toggleTheme">
    <Icon v-if="dark" class="default-icon-color" size="20px" name="weather/moon"/>
    <Icon v-else class="default-icon-color" size="20px" name="weather/sun"/>

    <HeaderPopup>
      <HeaderPopupItem name="Light" icon="weather/sun"/>
      <HeaderPopupItem name="Dark" icon="weather/moon"/>
      <HeaderPopupItem name="System" icon="hardware/display"/>
    </HeaderPopup>
  </div>
</template>

<script>
export default {
  data() {
    return {
      dark: false
    }
  },
  created() {
    this.setTheme(localStorage.darkTheme === 'true');

    // window.matchMedia("(prefers-color-scheme: dark)").addEventListener("change", e => console.log(e));
  },
  methods: {
    toggleTheme() {
      this.setTheme(!this.dark);
    },
    setTheme(dark) {
      const classes = document.documentElement.classList;

      if(dark) classes.add('dark');
      else classes.remove('dark');

      this.dark = dark;

      localStorage.darkTheme = dark;
    }
  }
}
</script>
