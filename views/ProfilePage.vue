<template>
  <header>
    <div
      class="profile_background"
      :style="{ backgroundImage: `url(${backgroundURL})` }"
    >
      <div>
        <h1>Profile</h1>
        <p>ID: {{ userId }}</p>
      </div>
    </div>
    <div class="container profile_mainInfo">
      <div class="pfp"></div>
    </div>
  </header>
</template>

<script>
import { useRoute } from "vue-router";
export default {
  setup() {
    const route = useRoute();
    return {
      userId: route.params.id,
    };
  },
  props: {
    backgroundURL: {
      type: String,
      default: "/images/pexels-pixabay-33597.jpg",
    },
  },
};
</script>

<style scoped>
.profile_background {
  height: 300px;
  background-size: cover;
  background-position: center;
}
</style>
