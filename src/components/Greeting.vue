<template>
  <div class="flex gap-4">
    <icon :name="icon" />
    <p class="text-h6 md:text-h5 lg:text-h4 uppercase font-bold" aria-label="Greeting">
      <span class="hidden md:inline-block font-normal">Hiện tại là </span> {{ text }}
    </p>
  </div>
</template>

<script>
import Icon from "./Icon.vue";

export default {
  components: {
    Icon,
  },
  props: {
    hour: Number,
  },
  computed: {
    text() {
      if (this.hour >= 5 && this.hour < 12) {
        return "Buổi Sáng";
      } else if (this.hour >= 12 && this.hour < 18) {
        return "Buổi Chiều";
      } else {
        return "Buổi Tối";
      }
    },
    icon() {
      return this.hour >= 5 && this.hour < 18 ? "sun" : "moon";
    },
  },
};
</script>
