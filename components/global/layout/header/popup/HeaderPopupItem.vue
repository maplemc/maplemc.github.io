<template>
  <div class="w-full px-8 py-2 flex items-center hover:bg-white/10">
    <Icon v-if="icon" class="default-icon-color mr-4" size="18px" :name="icon"/>
    <span class="font-sans-serif font-normal subtitle-text-color text-[16px]">{{ name }}</span>
  </div>
</template>

<script>
export default {
  props: {
    name: String,
    icon: String
  }
}
</script>
